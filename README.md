# Credit Risk Classification

![Python](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)

## Challenge Description

Dream Housing Finance là một công ty tài chính chuyên cung cấp các khoản vay mua nhà. Công ty hoạt động trên khắp các khu vực đô thị, bán đô thị và nông thôn. Hiện tại, quy trình xét duyệt khoản vay dựa vào nhân viên và mất nhiều thời gian. Vì vậy, mục tiêu là tự động hóa quy trình xét duyệt bằng cách xây dựng một mô hình dự đoán khả năng khách hàng được chấp thuận khoản vay. Điều này sẽ giúp công ty tập trung vào các khách hàng tiềm năng.

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

Bộ dữ liệu chứa các thông tin nhân khẩu học và lịch sử vay vốn của những khách hàng trước đây của công ty.

Attribute Information:

1. Loan_ID: Unique Loan ID
2. Gender: Male/ Female
3. Married: Applicant married status (Y/N)
4. Dependents: Number of dependents
5. Education: Applicant Education (Graduate/ Under Graduate)
Self_Employed: Self-employed (Y/N)
ApplicantIncome: Applicant income
CoapplicantIncome: Coapplicant income
LoanAmount: Loan amount in thousands
Loan_Amount_Term: Term of a loan in months
Credit_History: credit history meets guidelines
Property_Area: Urban / Semi-Urban / Rural
Loan_Status: Loan approved (Y/N)
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
