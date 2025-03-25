# Credit Risk Analysis Report

## Overview : 
In order to determine the eligibility criteria for sanctioning loans, an analysis was done on a historical loan dataset,  which shows the lending activity from a peer-to-peer lending service company. Analyzing this dataset provides insights into a borrower's likelihood of repaying a loan. This would  help lenders decide whether to approve or deny loan applications by predicting the likelihood of repayment.

### Information included in the dataset
The financial information included in this dataset are:
* loan_size –  The total amount of money being borrowed.
* interest_rate – The percentage rate at which interest is charged on the outstanding loan balance.
* borrower_income – The income or earnings of the borrower.
* debt_to_income Ratio (DTI) – The ratio of the borrower’s total monthly debt payments to their gross monthly income.
* number_of_accounts – The total count of credit accounts held by the borrower.
* derogatory_marks – Negative records on a borrower's credit report, such as bankruptcies, late payments, or collections. The more derogatory marks, the higher the risk of default.
* total_debt – The sum of all outstanding debts owed by the borrower.
* loan_status - The current status of the loan
    * loan_status(0) – Indicates the borrower repaid the loan.  
    * loan_status(1) – The borrower defaulted on the loan.

For the analysis, loan_status is taken as the target variable. Based on the loan status, the lender can predict if the customer will be able to pay the loan.
Since the loan status has two values (0 and 1), we applied binary classification, labeling 0 as a Healthy Loan and 1 as a High-Risk Loan.Since logistic regression works well for binary classification, we used this model for analysis.

### Stages of the Machine Learning Process for Analysis : 
The following stages of machine learning were carried for the purpose of analysis:  
* 1. Imported the dataset
* 2. Separated the data into features and labels. Here loan_status is taken as the label and  other columns as features
* 3. Split data into training and testing.
* 4. Trained a Logistic Regression model.
* 5. Made predictions on test data.
* 6. Evaluated the model using Confusion Matrix.
* 7. Generated a Classification Report for precision, recall and F1-score

## Results:
### Confusion Matrix
On analysing the confusion matrix, it is seen that
* 18673 healthy loans were classified correctly.
* 593 high risk loans were classified correctly.
* 86 healthy loans were incorrectly classified as high risk.
* 32 high risk loans were incorrectly classified as healthy.

### Classification Report 
![classification report](classification_report.png)
The classification report provides understanding on the precision, recall and F1-score:
* 1. Precision : This shows how many predicted positives are actually correct
    * Healthy Loans : 1 implies there are no false healthy loans. It is almost perfect.
    * High- Risk Loans : 0.87 implies 87% of the high risk loans were matched correctly. Only a few misclassifications were made.
* 2. Recall :  This shows how many actual positives were correctly predicted. 
    * Healthy Loans : This model was able to predict almost 100% of the actual healthy loans
    * High-Risk Loans : 95% of the actual high risk loans were identified correctly.
* 3. F1-score :  Measures the balance between precision and recall. 
    * Healthy Loans : This model was able to identify almost 100% of the actual healthy loans
    * High- Risk Loans : 91% of the actual high risk loans were identified correctly.

### Overall Metrics:
* 1. Accuracy = 0.99
* 2. The Macro Avg (0.94 Precision, 0.97 Recall, 0.95 F1-Score) gives an equal weight to both classes, regardless of class size.
* 3. The Weighted Avg (0.99 Precision, 0.99 Recall, 0.99 F1-Score) considers the class imbalance (if there are far more healthy loans than high-risk loans, this skews the score).

## Summary
In a nutshell, 
* Logistic regression is effective for interpretability.
* It works well with binary classifications.
* From the confusion matrix, it is seen that the misclassifications are far less than the correct classifications.
* From the classification report it is seen that the accuracy is 99%. This shows that overall 99% of the predictions are correct. It implies when the model approves a loan (predicts low risk), it is usually correct,thus, reducing the chance of lending to defaulters.
* A high Recall for High-Risk Loans is crucial for identifying potential defaulters.
* A 91% F1 score for high risk loans implies that the model is well balanced in identifying defaulters and minimizing misclassifications.




