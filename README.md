# credit-risk-classification

* Run credit_risk_classification.ipynb
* Sources are commented in code
* Analysis can be read below

## Overview of the Analysis

The purpose of this analysis was to train, test, and evaluate a logistic regression model that can identify the creditworthiness of borrowers. This model used several variables to determine creditworthiness including: loan size, interest rate, borrower income, debt to income ratio, number of accounts the borrower has, derogatory marks on the borrower's credit report, and total debt. 

In the data, loan size varied from $9,600 to $23,800 with interest rates ranging from 7.211% to 13.235%. Most loans in the data set were on the lower end of loan size and interest rate. Debt to income ratio varied from 0.381443 t0 0.714829, number of accounts varied between 4 and 16. No borrower had more than 3 derogatory marks. Total debt varied from $18,500 to $75,200. 

For this analysis, a dataset of historical lending activity from a peer-to-peer lending service company was used to build the model. First, this data was reviewed to ensure appropriateness for this analysis. Then, the data was split into two sets in order to train the logistic regression model and then to test the performance of the model. Logistic regression is a technique used to identify the relationship between two data factors, which is then used to predict one of those factors based on the other [1]. Next, the performance of the model was evaluated for accuracy and precision to determine the usefulness of the model. Following this evaluation, the training data was supplemented using random oversampling. Random oversampling "involves randomly duplicating examples from the minority class and adding them to the training dataset" [2]. Then the a logistic regression model was created using this new supplemented training set and evaluated for accuracy and precision. Finally, the two evaluations were compared to assess which model performed better. 


## Results

* Machine Learning Model 1:
  * Accuracy Score: 0.9918489475856377
  * Healthy Loan 
	Precision: 1.00
	Recall: 0.99
  * High Risk Loan
	Precision: 0.85
	Recall: 0.91
  * Confusion Matrix 
	([[18663,   102],
    [56,      563]])

* Machine Learning Model 2:
  * Accuracy Score: 0.9938093272802311
  * Healthy Loan 
	Precision: 1.00
	Recall: 0.99
  * High Risk Loan
	Precision: 0.84
	Recall: 0.99
  * Confusion Matrix 
	([[18649,   116],
    [4,       615]])

    
## Summary

In general, the second model appears to be performing the best with a higher accuracy score and higher recall for high risk loans. This model does however lose some precision for high risk loans. Both models preform well in accurately predicting true positives. 

The main differences are observed for high risk loans, which are arguable more important since lenders will use this model to mitigate their risk by identifying high risk loans accurately. The preferred model should have a high accuracy for true negatives and false positives to ensure high risk loans are accurately identified and that high risk loans are not mistakenly identified as healthy loans. For this we can look at the bottom row of the confusion matrix for each model, which displays false positives and true negatives respectively. Model 2 has better outcomes on this line than Model 1. 

Model 2 should be utilized if the lender believes that 4 false positives out of every 619 (0.646%) high risk loans is an acceptable risk. Model 1 should not be utilized as this ratio is much worse (9.047%). 



References 
[1] "What is Logistic Regression?" Amazon Web Services. https://aws.amazon.com/what-is/logistic-regression (accessed Feb. 18,2024). 
[2] J. Brownlee. "Random Oversampling and Undersampling for Imbalanced Classification." Machine Learning Mastery. https://machinelearningmastery.com/random-oversampling-and-undersampling-for-imbalanced-classification (accessed Feb. 18,2024). 
