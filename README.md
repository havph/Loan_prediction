# Credit Risk Classification

![Python](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)

## Problem Description

This project aims to classify credit risk based on financial transaction data. The objective is to develop a machine learning model that can accurately predict whether a customer belongs to a high-risk credit group or not, helping banks optimize their credit approval process and reduce potential bad debts.

## Project Structure

```
├── LICENSE
├── README.md           <- Project documentation.
├── notebooks           <- Jupyter notebooks containing data analysis and model training.
│   └── credit_risk.ipynb  <- Main notebook with data preprocessing and model training.
├── reports            <- Final analysis report in PDF format.
│   └── Report.pdf     <- Full research and results.
├── src                <- Source code folder.
│   ├── data           <- Datasets used for training and testing.
│   ├── model          <- Trained models and scripts.
│   └── utils          <- Helper functions and utilities.
```

## Dataset Information

The dataset consists of financial transactions and customer demographic information. It includes the following key columns:

- `customer_id`: Unique identifier for each customer.
- `age`: Customer's age.
- `income_level`: Categorized income level.
- `loan_amount`: The total loan amount taken by the customer.
- `transaction_history`: Records of past transactions.
- `credit_score`: The customer's credit score.
- `loan_status`: Binary label indicating good (0) or bad (1) credit status.

## Background Information

Credit risk assessment is a critical aspect of banking and financial management. Machine learning models can enhance the accuracy of risk classification, helping financial institutions:

- Reduce the risk of bad debts.
- Improve loan approval efficiency.
- Enhance customer relationship management.

By leveraging advanced machine learning techniques, this project aims to create a robust credit classification system that enables better decision-making.

## Objective

The main goal of this project is to develop a machine learning model capable of classifying customers into different credit risk categories. The model will help financial institutions mitigate risks by identifying potential defaulters early.

## Approach

1. **Data Preprocessing**:
   - Handling missing values and outliers.
   - Encoding categorical variables.
   - Feature scaling and transformation.

2. **Feature Engineering**:
   - Creating interaction terms between key financial indicators.
   - Generating new features from transaction history.
   - Implementing statistical transformations.

3. **Machine Learning Models**:
   - Logistic Regression
   - Decision Tree
   - Random Forest
   - Support Vector Machine (SVM)
   - Artificial Neural Networks (ANN)

4. **Performance Evaluation**:
   - Using metrics such as AUC-ROC, Precision, Recall, and F1-Score.
   - Conducting cross-validation and hyperparameter tuning.

5. **Model Optimization**:
   - Adjusting classification thresholds for optimal recall.
   - Implementing SMOTE for handling imbalanced datasets.
   - Fine-tuning hyperparameters.

## Results & Findings

- **Best Model**: Random Forest achieved the highest accuracy with an F1-score of **88%**.
- **Key Insights**:
  - Transaction history is a strong predictor of credit risk.
  - Customers with lower income and higher loan amounts have a higher probability of default.
  - Feature interactions significantly improved model performance.

## Future Work

- Implementing deep learning models for further improvements.
- Exploring alternative datasets for broader risk assessment.
- Integrating the model into a real-time credit scoring system.

## License

This project is licensed under the [MIT License](LICENSE).

## Author

- **Project Contributor: [Your Name]**
