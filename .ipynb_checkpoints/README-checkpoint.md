# Loan Approval Application


<b>Research question:</b> How well can classification models predict loan approval, and which regression model best predicts the loan amount?
Data source: Kaggle's Loan Dataset.

<b>Techniques:</b> Classification models (KNN, SVM, Logistic Regression, Random Forest, etc.) for approval prediction, and regression models (Linear Regression, Decision Trees) for loan amount prediction.

<b>Expected results:</b> Identification of the best-performing classification and regression models, providing insights into loan approval and amounts. 

<b>Importance:</b> This is important for helping buyers plan their purchases and negotiations based on loan outcomes. For financial insttutions to determine what features are important and ensure data collection is accurate for those features. For applicants, again what features are important and ensure that they provide the best support for those elements.


# About Data Set

We started with 614 rows of the data. After cleaning and handling null values our dataset consists of 592 loan applications. After imputing the values for Gender and Married columns we can use all the 614 rows.

<b>Gender Distribution:</b> The dataset consists predominantly of male applicants (502 out of 614).

<b>Marital Status:</b> Most applicants are married (401 out of 614), indicating that marital status might be a common factor in loan applications.

<b>Education Level:</b> The majority of applicants are graduates (480 out of 614), suggesting a potential link between education and loan approval.

<b>Self-Employment Status:</b> A large proportion of applicants are not self-employed (500 out of 614 recorded entries), implying that salaried employees may be more common in loan applications.

<b>Property Area:</b> Loans are distributed across urban, semi-urban, and rural areas, with the highest number of applications coming from semi-urban areas (233 out of 614).

<b>Loan Approval Rate:</b> The dataset shows a 69% approval rate (422 approved applications), while 31% of applications (192) were rejected.

# Data preperation and transformation

One-hot encoding was applied to categorical columns such as Gender, Married, Education, Self_Employed, and Property_Area to convert them into numerical representations, enabling the dataset to be used effectively in machine learning models.

The correlation matrix provides insights into the relationships between numerical features in the dataset. 

The correlation analysis indicates that Credit History has a strong positive correlation (0.5356) with Loan Amount, suggesting that applicants with a good credit history are more likely to receive higher loan amounts. On the other hand, Applicant Income shows a near-zero correlation (-0.0252) with Loan Amount, implying that income alone does not significantly determine the approved loan amount. This suggests that while income is considered, other factors such as creditworthiness and repayment history play a more crucial role in loan approval decisions.

To ensure ethical AI/ML and remove biases, I decided to remove the Gender column. The reasons include filling null values with "Male" and the narrow distribution of the data.

# Baseline model selection

For the first part of the problem, the target variable Loan_Status is categorical (Y (1) for approved, N (0) for rejected), this is a classification problem. The goal is to predict whether a loan will be approved or not based on applicant attributes. 
A baseline model should be simple yet effective for benchmarking. A Logistic Regression model is a strong initial choice.

For the second part of the problem, Loan Amount is a continuous numerical variable, this is a regression problem rather than a classification problem. The goal is to predict how much loan amount an applicant is likely to receive based on the features available in the dataset. In this case I choose the  Random Forest Regressor as the baseline model. It will handle the non-linear relationship between the input features and loan amount effectively, as it appears to be the case based on the data analysis.

# Modeling for the classification problem
For my problem, I considered classification models since the target variable was categorical. I evaluated multiple models, including Logistic Regression, Decision Tree, K-Nearest Neighbors (KNN), Support Vector Machine (SVM), and Random Forest Classifier.

# Evaluation Metrics for the classification problem
To determine the most optimal model, I used the following metrics:

Train Accuracy & Test Accuracy: Indicate how well the model generalizes to unseen data.

Precision: Measures the proportion of true positives among predicted positives, which is crucial when false positives have significant consequences.

Recall: Measures the proportion of actual positives correctly identified, important in scenarios where missing a positive instance is costly.

F1 Score: A balance between precision and recall, ensuring that neither metric dominates the evaluation.

Train Time: Important for assessing computational efficiency, especially for large datasets.

# Model Comparison & Selection for the classification problem

Logistic Regression performed well with the highest test accuracy (85.4%) and an F1 score of 0.901, making it a strong candidate for interpretability and performance.

Decision Tree had slightly lower accuracy (81.6%) but a good recall value (94.4%).

Random Forest had the highest train accuracy (95.1%) but slightly lower test accuracy (81.0%), indicating possible overfitting.

SVM had perfect recall (100%) but relatively lower accuracy (68.6%).

KNN underperformed with the lowest test accuracy (61.6%).

# Final Model Selection for the classification problem

Based on a balance of test accuracy, precision, recall, and F1 score, Logistic Regression emerged as the best choice. It provided the highest test accuracy with a strong F1 score while avoiding overfitting, making it the most optimal model for my problem.

# Regression problem to predict approved amount

For the regression problem to predict the approved amount, we considered multiple classification models—Logistic Regression, Decision Tree, K-Nearest Neighbors (KNN), and Random Forest (RForest)—to compare their performance. The evaluation metric used was test accuracy, as the models were initially treated as classification problems, likely due to categorical target labels. However, for a true regression problem, metrics such as Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and R² (coefficient of determination) should be considered.

Evaluation Metric Selection for regression part of the problem

    Mean Absolute Error (MAE)
    Mean Squared Error (MSE)
    R2 Score: Measures how well the model explains the variance in loan amounts. Closer to 1 means a better fit.

# Model Comparison and Selection to predict approved amount

Logistic Regression had the highest test accuracy (85.4%) and a short training time, making it efficient.

Decision Tree performed slightly worse (82.7%), but was still competitive.

KNN had the lowest accuracy (65.4%) and the longest training time.

Random Forest performed decently (80%) but had a higher training time.

Given that the problem is a regression task, Logistic Regression is not the ideal model since it is designed for classification. Instead, Random Forest Regression or Decision Tree Regression would be more suitable, as they can handle non-linearity in data and provide numerical predictions. Hyperparameter tuning should focus on minimizing errors (MSE, RMSE) rather than maximizing classification accuracy.

# Summary

Out of all loan applications, 69.43% were approved, while 30.57% were rejected. This indicates that a 2/3 of applicants successfully secured a loan. The approval trend suggests that applicants with favorable credit history, stable employment, and strong income profiles are more likely to be approved.

The most significant factor in loan approval is credit history. From Bank/Financial Institution perspective they need to ensure they have most recent credit history to ensure accurate approvals. Applicants need to maintain good credit history. A higher increases the chances of approval and adding co-applicant income will help.

This project provided valuable insights into data preparation and analysis by applying both classification and regression techniques to the same dataset. For the classification problem, I used the Loan Approved (Y/N) column as the target variable, training models such as Logistic Regression, Decision Tree, KNN, and Random Forest to predict loan approval status. Logistic Regression performed the best with 85.4% accuracy.

For the regression problem, I used the Loan Amount column as the target variable to predict the approved amount. This helped in understanding how different modeling approaches can be applied to the same dataset for multiple types of analysis. The project enhanced my knowledge of data preprocessing, feature selection, hyperparameter tuning, and model evaluation, reinforcing the importance of choosing the right model based on the problem type.

# Future Work

Generate synthetic data: The dataset is small, I beleive, the accuracy can be increased by generating synthetic data <br>
Try the regression and classification problem using the neural networks
