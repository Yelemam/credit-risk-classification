# credit-risk-classification
## Overview of the Analysis

The purpose of this analysis is to develop and evaluate a machine learning model that classifies loans as either "healthy" or "high-risk" based on historical
lending data. This model will support a peer-to-peer lending service in assessing the creditworthiness of potential borrowers, helping to make informed 
lending decisions and minimize defaults.

## Dataset Details

The dataset contains over 10,000 rows of historical loan data with the following features:

 - loan_size: The size of the loan requested.
 - interest_rate: The interest rate associated with the loan.
 - borrower_income: The annual income of the borrower.
 - debt_to_income: The ratio of debt to income for the borrower.
 - num_of_accounts: Number of financial accounts held by the borrower.
 - derogatory_marks: Number of negative marks on the borrower’s credit report.

The target variable, loan_status, indicates whether a loan is:

 - 0 (Healthy Loan): Low risk of default.
 - 1 (High-Risk Loan): High risk of default.

## Business Context
This analysis aims to enhance lending decisions by identifying high-risk loans, which can help reduce defaults and improve financial outcomes for the lending
company. Accurately identifying healthy loans ensures trust and efficiency in lending operations.


In this analysis, we used logistic regression, a statistical method commonly used for binary classification problems. Logistic regression is particularly suitable for this task because it predicts the probability of an outcome belonging to one of two categories (healthy or high-risk loans). Its simplicity and interpretability make it an effective starting point for this type of financial analysis.

### Steps in the Analysis

1. **Data Preparation**: The dataset was loaded, and we separated the labels (`loan_status`) from the features.
2. **Data Splitting**: The data was divided into training and testing sets to evaluate model performance.
3. **Model Training**: We trained a logistic regression model using the training data.
4. **Prediction and Evaluation**: Predictions were made on the test set, followed by generating a confusion matrix and a classification report to evaluate the model's accuracy, precision, and recall.

## Results

The logistic regression model was evaluated for both "healthy loans" (0) and "high-risk loans" (1) using various metrics. The following results were obtained:


- **Confusion Matrix**:
[[14924 77] [ 31 476]]
 - True Negatives (14924): Healthy loans correctly predicted.
 - False Positives (77): Healthy loans incorrectly predicted as high-risk.
 - False Negatives (31): High-risk loans incorrectly predicted as healthy.
 - True Positives (476): High-risk loans correctly predicted.


- **Classification Report**:

- **Healthy Loan (0)**:
  - Precision: 1.00 (Perfect precision means no false positives for healthy loans.)
  - Recall: 0.99 (Almost all healthy loans were correctly identified.)
  - F1 Score: 1.00 1.00 (The harmonic mean of precision and recall.)

  
- **High-Risk Loan (1)**:
  - Precision: 0.86 (A few healthy loans were misclassified as high-risk.)
  - Recall: 0.94 (Most high-risk loans were identified correctly.)
  - F1 Score: 0.90 0.90 (Good balance of precision and recall.)
  
- **Overall Metrics**:
  - **Accuracy**: 99%
  - **Macro Average** (average of precision and recall): 0.93 
    - precision: 0.93 
    - recall: 0.97
  - **Weighted Average** (weighted by support):
     - precision: 0.99
     - recall: 0.99
     
** Key Takeaways ** 

- The model is highly effective at predicting healthy loans with perfect precision and nearly perfect recall.
- It performs strongly on high-risk loans, achieving a precision of 0.86 and recall of 0.94. While a few high-risk loans are missed, the model reliably flags most risky cases.
- The overall accuracy of 99% demonstrates that this model is well-suited for deployment.

### Interpretation of Results

- **Healthy Loans (0)**: The model performs exceptionally well in predicting healthy loans with a precision and recall close to perfect, meaning that almost all healthy loans are correctly identified and very few false positives are generated.
- **High-Risk Loans (1)**: The model also performs strongly in identifying high-risk loans with a precision of 0.86 and a recall of 0.94. This indicates that while a few false positives exist, the model is effective at capturing high-risk cases, which is crucial for minimizing potential defaults.

## Summary

The logistic regression model demonstrates exceptional performance in classifying loans as "healthy" or "high-risk," achieving an overall accuracy of 99%.

** Key Strengths **

- Reliability for Healthy Loans:
With perfect precision and recall (1.00), the model ensures that healthy loans are rarely misclassified as high-risk, preserving borrower trust and
operational efficiency.

- Effectiveness for High-Risk Loans:
The model achieves a precision of 0.86 and a recall of 0.94, ensuring that most high-risk loans are flagged correctly. This reduces potential financial losses 
due to defaults.

** Business Impact ** 
- Accurately identifying high-risk loans minimizes financial risks while ensuring lending decisions are data-driven and reliable.
- The high accuracy and strong recall for high-risk loans can significantly improve the company's portfolio management and resource allocation.

** Recommendations **
To further enhance the model’s performance:

- Algorithm Exploration:
Consider testing advanced machine learning models like Random Forests, Gradient Boosting, or ensemble methods to capture more complex patterns in the data.

- Data Expansion:
Collect more diverse data to improve the model’s generalizability and robustness.

- Regular Updates:
Periodically retrain the model with new data to adapt to evolving lending patterns.

** Conclusion **
Given the strong performance metrics, this logistic regression model is well-suited for deployment. It provides a reliable foundation for identifying 
high-risk loans and optimizing lending decisions. With minor enhancements, it could achieve even greater precision and recall, further reducing financial
 risk and maximizing operational efficiency.
 

### Additional Considerations

1. **Further Improvements**: To improve precision for high-risk loans, consider exploring other classification algorithms, such as Random Forest or Gradient Boosting, which may capture more complex patterns in the data.
2. **Data Updates**: Regularly update the model with new data to ensure it remains effective as lending patterns evolve.


# Glossary of Terms
** Precision: **

- Definition: The proportion of positive identifications that were actually correct.
- Example: If the model predicts 100 loans as high-risk and 86 are actually high-risk, the precision is 86%.
- Importance: Measures how often the model is correct when it predicts a loan is high-risk.

** Recall: **

- Definition: The proportion of actual positives that were correctly identified.
- Example: If there are 100 actual high-risk loans and the model identifies 94 of them, the recall is 94%.
- Importance: Measures the model’s ability to find all high-risk loans.

** F1 Score:** 

- Definition: The harmonic mean of precision and recall, balancing their trade-offs.
- Formula: F! = 2 X Precision*Recall / Precision+Recall 
- Importance: Useful when precision and recall are equally important.

** Accuracy: **

- Definition: The proportion of all predictions that the model got correct.
- Formula: Accuracy = (True Positives + True Negatives )/ Total Predictions 
- Example: If the model makes 1,000 predictions and 990 are correct, the accuracy is 99%.
- Importance: Provides an overall measure of the model's performance but can be misleading for imbalanced datasets.

** Confusion Matrix: **

- Definition: A table used to evaluate the performance of a classification model by showing true positives, true negatives, false positives, and false negatives.
- Example:
 [[14924    77]   # Healthy loans
 [   31   476]]  # High-risk loans
- Importance: Breaks down the performance of the model by outcome type.

### Acknowledgment

This project was completed with some assistance from AI tools to help refine the analysis and improve the clarity of the results. AI support was used for 
some refinement and to enhance the wording of the findings.
