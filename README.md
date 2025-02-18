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

# ** 2&3. XỬ LÝ DỮ LIỆU**

## 1. Thu thập và tiền xử lý dữ liệu

- **Thay đổi tên cột** để thuận tiện cho việc xử lý.
- **Lọc dữ liệu**: Loại bỏ các bản ghi không ghi nhận nợ, giữ lại **29.956 dòng** và **50 cột**.
- **Mã hóa lại nhóm nợ**: Chuyển đổi nhóm nợ từ **5 mức** về **2 mức**:
  - `0`: Nợ tốt.
  - `1`: Nợ xấu.

## 2. Phân tích và mô tả dữ liệu

### Phân loại biến:
- **Categorical (Biến phân loại)**:
  - *Nomial* (Không thể sắp xếp thứ tự): `loc1`, `vn_mar`, `most_act_m21`, `most_act_j21`.
  - *Ordinal* (Có thể sắp xếp thứ tự): `term_j21`.

- **Numerical (Biến số học)**:
  - *Continuous (Liên tục)*: `amt_w`, `max_amt_w`, `min_amt_w`, `amt_m`, `max_amt_m`, `min_amt_m`, `amt_3m`, `max_amt_3m`, `min_amt_3m`, `total_amt_m21`, `total_amt_j21`, `saving_m21_HS`, `saving_j21_HS`, `bal_j21`, `nom_int_j21`, `real_int_j21`.
  - *Discrete (Rời rạc)*: `resid_p`, `resid_d`, `resid_w`, `most_act_m21_cnt`, `dist_pay_w`, `dist_trans_w`, `dist_ref_w`, `cnt_pay_w`, `dist_pay_m`, `dist_trans_m`, `dist_ref_m`, `cnt_pay_m`, `dist_pay_3m`, `dist_trans_3m`, `dist_ref_3m`, `cnt_pay_3m`, `total_act_m21`, `total_act_j21`, `total_login_m21_HS`, `total_login_j21_HS`, `total_savings_21_HS`, `rd_id`, `nhomno_j21`, `cat_j21`, `sub_prod_j21`, `sec_j21`, `prod_j21`.

### Kiểm tra dữ liệu bị thiếu (NULL):
- Các biến có hơn **35% giá trị NULL** bị loại bỏ.
- Một số biến có NULL được thay thế bằng **giá trị phổ biến (mode)** hoặc **giá trị hợp lý**.

## 3. Làm sạch dữ liệu (Data Wrangling)
- Xử lý giá trị không hợp lệ:
    - Tính toán độ tuổi từ năm sinh và loại bỏ giá trị không hợp lệ (<18 hoặc >100 tuổi).
- Xử lý dữ liệu bị thiếu:
    - Điền giá trị NULL bằng mode (giá trị phổ biến nhất) theo nhóm tuổi & giới tính.
    - Thay thế NULL bằng 0 cho các giao dịch không phát sinh trong tháng.
    - Sử dụng KNN Imputer để điền dữ liệu thiếu cho các biến tài chính.
- Xử lý ngoại lệ:
    - Loại bỏ các giá trị âm trong tổng giao dịch và tổng số giao dịch tháng 3, tháng 6.
- Chuẩn hóa dữ liệu:
    - Dữ liệu dạng số đã có phân phối chuẩn, không cần biến đổi thêm.

