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
   






      





