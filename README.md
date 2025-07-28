# Bank-Loan-Report-Analysis



### Introduction to the Financial Loan Dataset

This dataset provides a comprehensive look at personal loans, containing **38,576 records** and **24 distinct features**. It offers a rich source of information for understanding lending patterns, borrower demographics, and loan outcomes. The data encompasses various aspects of each loan, including borrower details, loan characteristics, and repayment status, making it ideal for a wide range of financial analyses, from credit risk assessment to predictive modeling.

-----

### Data Composition and Key Features

The dataset is structured with a mix of numerical and categorical features, providing both quantitative and qualitative insights.

#### Borrower Information

  * **Demographics**: The dataset includes basic demographic information such as the borrower's **address state**, **home ownership** status (the majority either `RENT` or have a `MORTGAGE`), and **employment length**. A significant number of borrowers have **10+ years of employment**, suggesting a stable employment base.
  * **Financial Profile**: Key financial metrics include **annual income**, with a mean of approximately **$69,644**, and a **debt-to-income (DTI) ratio**. The annual income is right-skewed, with a few high-earning individuals.

#### Loan Characteristics

  * **Loan Amount and Terms**: Loan amounts range from **$500 to $35,000**, with an average of **$11,296**. The loans are offered with two primary terms: **36 months** (the most common) and **60 months**.
  * **Purpose of Loan**: The primary reason for borrowing is **debt consolidation**, followed by **credit card** refinancing. Other significant purposes include **home improvement**, **major purchases**, and **small business** loans.
  * **Interest Rates and Grades**: The interest rate on loans varies from **5.42% to 24.59%**, with an average of **12.05%**. Each loan is assigned a **grade** (A to G) and a **sub-grade**, which likely reflects the lender's assessment of risk, with Grade 'B' being the most common.

#### Loan Status and Repayment

  * **Loan Status**: The dataset tracks the status of each loan. A majority of the loans are **"Fully Paid,"** while a smaller but significant portion are **"Charged Off,"** indicating a default. A small number of loans are **"Current."**
  * **Payment Information**: The dataset also contains details about the total amount paid by the borrower (`total_payment`).

-----

### Analytical Approach and Potential Uses

This dataset is well-suited for a variety of analytical projects:

  * **Credit Risk Modeling**: The `loan_status` column can be used as a target variable to build models that predict the likelihood of a borrower defaulting on a loan. Features like `grade`, `dti`, `annual_income`, and `emp_length` would be crucial for such a model.
  * **Exploratory Data Analysis (EDA)**: The data can be explored to uncover relationships between different variables. For example, one could analyze how interest rates vary with loan purpose or how loan grades are distributed across different states.
  * **Customer Segmentation**: Borrowers could be segmented into different groups based on their demographic and financial profiles. This can help in understanding the customer base better and in tailoring financial products.

### Data Quality

The dataset is generally clean, with one notable exception: the **`emp_title`** column has **1,438 missing values**. This should be addressed during any data preprocessing phase. All other columns are complete, and the data types are consistent.

This detailed overview provides a solid foundation for anyone looking to understand and work with this financial loan dataset.


#	ANALYZING THE DATA USNING SQL SERVER MANAGEMENT

### KEY PERFORMANCE INDICATORS 
   1.	TOTAL LAON APPLICATIONS
   
      select count(id)as Total_Loan_Applications from financial_loan

   
   <img width="275" height="105" alt="image" src="https://github.com/user-attachments/assets/bb5f829b-eb6e-4f3b-ba18-9769d348e789" />

   2.	TOTAL LOAN APPLICATION MONTHS TO DATE, 12TH MONTHS

      select count(id)as MTD_Total_Loan_Applications from financial_loan
      where MONTH(issue_date) = 12 and YEAR(issue_date) = 2021

   <img width="327" height="70" alt="image" src="https://github.com/user-attachments/assets/2e476452-da26-4619-aa7f-6ef60c90fe96" />

   3.	TOTAL LOAN APPLICATION MONTHS TO DATE, 12TH MONTHS
      
      select count(id)as PMTD_Total_Loan_Applications from financial_loan – NOVEMBER
      where MONTH(issue_date) = 11 and YEAR(issue_date) = 2021


   <img width="334" height="73" alt="image" src="https://github.com/user-attachments/assets/a664a00f-10da-4fa8-82bc-557aab525a1d" />

   4.	TOTAL FUNDED AMOUNT

      SELECT SUM(loan_amount) AS Total_funded_amount FROM financial_loan


   <img width="263" height="83" alt="image" src="https://github.com/user-attachments/assets/c52ebf7e-15e2-4a1d-9ffe-81bd332b73f3" />

   5.TOTAL FUNDED AMOUNT MTD 
       
     SELECT SUM(loan_amount) AS MTD_Total_funded_amount FROM financial_loan 
     where MONTH(issue_date) = 12 and YEAR(issue_date) = 2021


   <img width="253" height="75" alt="image" src="https://github.com/user-attachments/assets/ffd16651-561b-4e08-b181-bb4890919086" />
   
  6.	TOTAL FUNDED AMOUNT PREVIOUS MONTHS , PMTD, (NOV)

    SELECT SUM(loan_amount) AS PMTD_Total_funded_amount FROM financial_loan 
    where MONTH(issue_date) = 11 and YEAR(issue_date) = 2021
  <img width="316" height="69" alt="image" src="https://github.com/user-attachments/assets/012e0818-7c76-4033-8301-93488e3bbb57" />

   7. TOTAL AMOUNT RECEIVED BY BANK THORUGH USERS

    SELECT SUM(total_payment) AS Total_Amount_recieved FROM financial_loan

   <img width="283" height="80" alt="image" src="https://github.com/user-attachments/assets/6cda7079-d9bc-4ceb-be38-87f5ac493699" />
   
   8.	TOTAL AMOUNT RECEIVED BY BANK THORUGH USERS  MTD

    SELECT SUM(total_payment) AS MTD_Total_Amount_recieved FROM financial_loan
    where MONTH(issue_date) = 12 and YEAR(issue_date) = 2021
   <img width="280" height="80" alt="image" src="https://github.com/user-attachments/assets/a2c30f25-5ad2-41ad-8dac-368f965b82c9" />

   9. TOTAL AMOUNT RECEIVED BY BANK THORUGH USERS  PMTD
       
    SELECT SUM(total_payment) AS PMTD_Total_Amount_recieved FROM financial_loan
    where MONTH(issue_date) = 11 and YEAR(issue_date) = 2021 
   <img width="319" height="64" alt="image" src="https://github.com/user-attachments/assets/17b3f43c-4b2b-4dc5-9839-d5da0f2841a3" />

   10. AVG_INTREST_RATE  OF BANK
       
    SELECT ROUND(AVG(int_rate),4) * 100 AS Avg_Intrest_Rate FROM financial_loan
   <img width="219" height="64" alt="image" src="https://github.com/user-attachments/assets/dfe3e5a3-459c-4edb-95b4-d8486fba406f" />
   
   11. AVG_INTREST_RATE  OF BANK   MTD

    SELECT ROUND(AVG(int_rate),4) * 100 AS MTD_Avg_Intrest_Rate FROM financial_loan 
    where MONTH(issue_date) = 12 and YEAR(issue_date) = 2021
   <img width="263" height="72" alt="image" src="https://github.com/user-attachments/assets/af2dc8f9-ab6a-4d04-a33e-7e3eb5121a06" />

   12.AVG_INTREST_RATE  OF BANK PMTD 

    SELECT ROUND(AVG(int_rate),4) * 100 AS PMTD_Avg_Intrest_Rate FROM financial_loan 
    where MONTH(issue_date) = 11 and YEAR(issue_date) = 2021
   <img width="292" height="80" alt="image" src="https://github.com/user-attachments/assets/fd15ea8c-b551-4d8c-95f4-ad24e7ca355d" />
   
   13. AVG_DTI
       
    SELECT ROUND(AVG(dti),4) * 100 AS Average_DTI FROM financial_loan
   <img width="203" height="77" alt="image" src="https://github.com/user-attachments/assets/49dda2ce-7611-4e5f-83b1-cc1127e93b93" />

   14. AVG_DTI MTD

    SELECT ROUND(AVG(dti),4) * 100 AS MTD_Average_DTI FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021



    




     

     






      





