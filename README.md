# Credit Risk Classification

![Python](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)

## Challenge Description

Dream Housing Finance là một công ty tài chính chuyên cung cấp các khoản vay mua nhà. Công ty hoạt động trên khắp các khu vực đô thị, bán đô thị và nông thôn. Hiện tại, quy trình xét duyệt khoản vay dựa vào nhân viên và mất nhiều thời gian. Vì vậy, mục tiêu là tự động hóa quy trình xét duyệt bằng cách xây dựng một mô hình dự đoán khả năng khách hàng được chấp thuận khoản vay. Điều này sẽ giúp công ty tập trung vào các khách hàng tiềm năng.

## Workflow stages
Solution được thực hiện qua 7 bước sau:

1. Problem definition.
2. Acquire data.
3. Wrangle, prepare, cleanse the data.
4. Analyze, identify patterns, and explore the data.
5. Model, predict and solve the problem.
6. Visualize, report, and present the problem solving steps and final solution.
7. Supply or submit the results.

## Dataset Information

Bộ dữ liệu chứa các thông tin nhân khẩu học và lịch sử vay vốn của những khách hàng trước đây của công ty.

Attribute Information:

1. Loan_ID: Unique Loan ID
2. Gender: Male/ Female
3. Married: Applicant married status (Y/N)
4. Dependents: Number of dependents
5. Education: Applicant Education (Graduate/ Under Graduate)
6. Self_Employed: Self-employed (Y/N)
7. ApplicantIncome: Applicant income
8. CoapplicantIncome: Coapplicant income
9. LoanAmount: Loan amount in thousands
10. Loan_Amount_Term: Term of a loan in months
11. Credit_History: credit history meets guidelines
12. Property_Area: Urban / Semi-Urban / Rural
13. Loan_Status: Loan approved (Y/N)
    
# **1. Problem Definition**
Dream Housing Finance muốn tự động hóa quy trình xét duyệt khoản vay dựa trên thông tin khách hàng. Mục tiêu của bài toán là xây dựng một mô hình dự đoán xem khách hàng có được duyệt khoản vay hay không.

**Xác định biến mục tiêu:**


- **Biến mục tiêu (target variable):** là biến muốn dự đoán hoặc giải thích dựa trên các biến đầu vào (biến độc lập hoặc đặc trưng - features).
- Biến mục tiêu của mô hình dự đoán nhóm xây dựng là: **Loan_Status**

# **2&3. XỬ LÝ DỮ LIỆU**

## **1. Thu thập và tiền xử lý dữ liệu**
- **Nhập dữ liệu** từ file CSV chứa thông tin về các khoản vay.
- **Chuyển đổi dữ liệu**: Đặt `Loan_ID` làm chỉ mục thay vì giữ nguyên dạng cột.
- **Phân loại biến**:
  - **Categorical (Phân loại)**:
    - **Nominal (Không có thứ tự)**: Giới tính, tình trạng hôn nhân, nghề nghiệp tự do, khu vực tài sản, trạng thái khoản vay.
    - **Ordinal (Có thứ tự)**: Trình độ học vấn, số lượng người phụ thuộc.
  - **Numerical (Số liệu)**:
    - **Continuous (Liên tục)**: Thu nhập của người vay, thu nhập của người đồng vay, số tiền vay.
    - **Discrete (Rời rạc)**: Thời hạn vay, lịch sử tín dụng.
- **Xử lý dữ liệu bị thiếu**:
  - **Xác định các cột có giá trị NULL** và kiểm tra phân phối dữ liệu.
  - **Điền dữ liệu thiếu**:
    - Các biến phân loại được điền bằng **giá trị phổ biến nhất (mode)**.
    - Các biến số được điền bằng **trung vị (median)** do không tuân theo phân phối chuẩn.

## **2. Làm sạch dữ liệu (Data Wrangling)**
- **Xử lý dữ liệu phân loại (Categorical)**
  - Chuyển đổi trạng thái khoản vay (`Loan_Status`) thành **0 và 1** (Từ chối/Chấp thuận).
  - Mã hóa biến **giới tính, trình độ học vấn, tình trạng hôn nhân, nghề nghiệp tự do** thành nhị phân (0/1).
  - Áp dụng **One-Hot Encoding** cho các biến có nhiều hơn hai giá trị (số người phụ thuộc, khu vực tài sản).
- **Chuẩn hóa dữ liệu số (Numerical)**
  - Dùng **MinMaxScaler** để đưa các giá trị về phạm vi (0,1) giúp mô hình hoạt động hiệu quả hơn.

## **3. Kết quả**
- Dữ liệu đã được **làm sạch và chuẩn hóa**, sẵn sàng để xây dựng mô hình dự đoán.

