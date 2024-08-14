# Beta Bank Customer Churn Prediction
## Project Overview
Beta Bank is facing a challenge with customer retention, as customers are leaving the bank at a steady rate. It has been determined that retaining existing customers is more cost-effective than acquiring new ones. The goal of this project is to build a predictive model that can accurately forecast whether a customer will leave the bank in the near future, enabling proactive measures to be taken to retain these customers.

## Objective
- Primary Goal: Develop a machine learning model to predict customer churn with the highest possible F1 score.
- Secondary Goal: Measure the AUC-ROC metric and compare it with the F1 score to evaluate the model’s performance.

## Data Source
The dataset contains various features that describe customer behavior and demographics, including:

- RowNumber: Data string index
- CustomerId: Unique customer identifier
- Surname: Customer's surname
- CreditScore: Customer's credit score
- Geography: Customer's country of residence
- Gender: Customer's gender
- Age: Customer's age
- Tenure: Duration of the customer's relationship with the bank in years
- Balance: Customer's account balance
- NumOfProducts: Number of banking products the customer uses
- HasCrCard: Indicator of whether the customer has a credit card
- IsActiveMember: Indicator of whether the customer is an active member
- EstimatedSalary: Customer's estimated salary
- Exited: Target variable indicating if the customer has left the bank (1) or not (0)

## Tools and Libraries
- Pandas: For data manipulation and analysis.
- Scikit-learn: For model training, evaluation, and preprocessing tasks.
- 
## Project Workflow
1. Data Preprocessing
- Dropped irrelevant columns: Removed Surname, CustomerID, and RowNumber as they do not contribute to the model’s predictive capabilities.
- Checked data types: Ensured all data types were appropriate for analysis.
- Handled missing values: Detected and filled missing values in the Tenure column using the median, based on the Shapiro-Wilk test results.
- Checked for duplicates: Verified that no duplicates existed in the dataset.
- Categorical encoding: Applied One-Hot Encoding to the categorical variables Geography and Gender to prepare them for the model.
2. Exploratory Data Analysis (EDA)

Pivot Table on Account Balances and Product Engagement:

- Identified that customers from Germany generally have higher account balances compared to other regions.
- Observed that the average number of products used by customers is consistent across regions and genders.

Histogram of Age Distribution:

- Found that most customers who churn are aged between 30 and 39.

Bar Chart of Churn Rate by Geography:

- Revealed that Germany has the highest churn rate (32.44%), despite having higher average account balances.

Box Plot of Balances by Exited Status:

- Showed that customers who stay tend to have higher account balances than those who leave.

Stacked Bar Chart of Product Usage by Churn Status:

- Indicated that customers with fewer products are more likely to churn.

3. Model Training and Evaluation

Class Imbalance Handling:

- The dataset had a significant class imbalance, with 20.37% of customers having churned.
- Implemented upsampling to balance the dataset and shuffled the data to ensure randomness.
  
Model Testing:

- Tested multiple models, including Decision Tree, Logistic Regression, and Random Forest.
- Found that Random Forest provided the best performance, especially after fine-tuning with upsampling and shuffling.
  
4. Model Performance
F1 Score:

- Achieved an F1 score of 0.61 on the test set, exceeding the project’s requirement of 0.59.
- This indicates a solid balance between precision and recall in the model's predictions.
  
AUC-ROC Score:

- Achieved an AUC-ROC score of 0.85, demonstrating that the model is effective at distinguishing between customers who will churn and those who will not.
  
## Conclusion
The developed model successfully predicts customer churn for Beta Bank, achieving an F1 score of 0.61 and an AUC-ROC score of 0.85. The model performs well, particularly in identifying customers likely to churn, which is critical for proactive retention strategies. Further refinements could focus on improving the recall for the minority class and testing additional algorithms or ensemble methods.
