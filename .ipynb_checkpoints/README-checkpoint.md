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

# Baseline model selection

For the first part of the problem, the target variable Loan_Status is categorical (Y (1) for approved, N (0) for rejected), this is a classification problem. The goal is to predict whether a loan will be approved or not based on applicant attributes. 
A baseline model should be simple yet effective for benchmarking. A Logistic Regression model is a strong initial choice.

For the second part of the problem, Loan Amount is a continuous numerical variable, this is a regression problem rather than a classification problem. The goal is to predict how much loan amount an applicant is likely to receive based on the features available in the dataset. In this case I choose the  Random Forest Regressor as the baseline model. It will handle the non-linear relationship between the input features and loan amount effectively, as it appears to be the case based on the data analysis.

# Evaluation Metric Selection


Evaluation Metric Selection for classification part of the problem
    Train Time
    Train Accuracy
    Test Accuracy
    Precision
    F1 Score
    Recall  

Evaluation Metric Selection for regression part of the problem
    Mean Absolute Error (MAE)
    Mean Squared Error (MSE)
    R2 Score: Measures how well the model explains the variance in loan amounts. Closer to 1 means a better fit.

# Summary
Out of all loan applications, 69.43% were approved, while 30.57% were rejected. This indicates that a 2/3 of applicants successfully secured a loan. The approval trend suggests that applicants with favorable credit history, stable employment, and strong income profiles are more likely to be approved.

The most significant factor in loan approval is credit history. From Bank/Financial Institution perspective they need to ensure they have most recent credit history to ensure accurate approvals. Applicants need to maintain good credit history. A higher increases the chances of approval and adding co-applicant income will help.
