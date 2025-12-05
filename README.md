# Predicting-Loan-Approval-using-R
This project focuses on developing a robust machine learning model to predict loan approval eligibility for the Dream Housing Finance Company

The primary goal of this project is to automate the loan eligibility process to eliminate manual paperwork, reduce processing delays, prevent data entry errors, and enhance overall operational efficiency. 

The project evaluates and compares the performance of two classification algorithim: Random Forest and XGBoost, to identify the most reliable approach for real-time integration into the company's system. 
#### Objectives of this Project
To develop a reliable predictive model that determines a customer's loan approval status (Y or N).

To evaluate and compare the predictive accuracy and performance of Random Forest and XGBoost models.

To identify the key factors that most significantly influence loan approval decisions.

### Methodology

The entire analysis and modeling process was conducted using R.

##### Data Source and Features

The datasets were sourced from Kaggle
- Training Data (loan_train.csv) which has  614 entries and 13 columns
- Testing Data (loan_test.csv) which has 367 entries and 12 columns
- 
##### Data Preprocessing and EDA
Irrelevant Feature Removal: The unique identifier column, Loan_ID, was dropped as it holds no predictive value
Handling of missing values: For numerical features like LoanAmount (which showed a right-skewed distribution), missing values were imputed using the mean to reflect the overall magnitude of the loan size. 
For categorical features like Credit_History and Loan_Amount_Term, missing values were imputed using the mode.
Feature Engineering: The categorical value '3+' in the Dependents column was converted to the numerical value 3 for consistency and model interpretability.

###### Exploratory Data Analysis (EDA)

A Correlation Heatmap revealed a significant positive correlation of 0.54 between Credit_History and Loan_Status, suggesting it is the strongest predictor.

<img width="849" height="721" alt="image" src="https://github.com/user-attachments/assets/077308e3-b459-4d5f-9cb1-9a30a552abb9" />


###### Model Training and Evaluation
Both Random Forest and XGBoost models were trained and evaluated using a 5-fold cross-validation approach with hyperparameter tuning to ensure robust performance and mitigate overfitting. 
### Results and Key Insights
Model Performance Comparison

<img width="547" height="203" alt="image" src="https://github.com/user-attachments/assets/12fab08d-ccfc-487c-bd1e-056ebc1e3e1f" />

Random Forest is the preferred model, showing higher accuracy and better stability (lower standard deviation) in predicting loan approval status compared to XGBoost. 

#### Feature Importance
Both models consistently identified the same top three most impactful features:
Credit_History: Emerged as the most critical determinant of loan approval, with the highest impact on model splits.
ApplicantIncome: The primary source of income is the second most important factor, directly impacting an applicant's likelihood of getting approval.
LoanAmount: The requested loan amount is also a key factor, with stricter criteria (higher scrutiny) applied to larger loans.

#### Future Improvement Suggestions for this project include:

Data Expansion: Incorporating a wider range of data from multiple financial institutions to reduce potential bias and create models that better reflect real-world situations. 
Advanced Feature Engineering: Integrating external features such as macroeconomic data or interest rates to enhance the model's predictive ability.
Real-Time Deployment: Integrating the optimized Random Forest model into a real-time application programming interface for immediate decision-making and improved customer experience.
