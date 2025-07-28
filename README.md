# Bank-Loan-Report-Analysis

```python?code_reference&code_event_index=2
import pandas as pd

# Load the dataset
df = pd.read_csv('financial_loan.csv')

# Display the first few rows
print("First 5 rows of the dataset:")
print(df.head())

# Get a concise summary of the dataframe
print("\nDataFrame Info:")
df.info()

# Get descriptive statistics for numerical columns
print("\nDescriptive Statistics:")
print(df.describe())

# Check for missing values
print("\nMissing Values per Column:")
print(df.isnull().sum())

```

```text?code_stdout&code_event_index=2
First 5 rows of the dataset:
        id address_state application_type emp_length              emp_title grade home_ownership  issue_date last_credit_pull_date last_payment_date  loan_status next_payment_date  member_id purpose sub_grade        term verification_status  annual_income     dti  installment  int_rate  loan_amount  total_acc  total_payment
0  1077430            GA       INDIVIDUAL   < 1 year                  Ryder     C           RENT  11-02-2021            13-09-2021        13-04-2021  Charged Off        13-05-2021    1314167     car        C4   60 months     Source Verified        30000.0  0.0100        59.83    0.1527         2500          4           1009
1  1072053            CA       INDIVIDUAL    9 years         MKC Accounting     E           RENT  01-01-2021            14-12-2021        15-01-2021   Fully Paid        15-02-2021    1288686     car        E1   36 months     Source Verified        48000.0  0.0535       109.43    0.1864         3000          4           3939
2  1069243            CA       INDIVIDUAL    4 years  Chemat Technology Inc     C           RENT  05-01-2021            12-12-2021        09-01-2021  Charged Off        09-02-2021    1304116     car        C5   36 months        Not Verified        50000.0  0.2088       421.65    0.1596        12000         11           3522
3  1041756            TX       INDIVIDUAL   < 1 year    barnes distribution     B       MORTGAGE  25-02-2021            12-12-2021        12-03-2021   Fully Paid        12-04-2021    1272024     car        B2   60 months     Source Verified        42000.0  0.0540        97.06    0.1065         4500          9           4911
4  1068350            IL       INDIVIDUAL  10+ years          J&J Steel Inc     A       MORTGAGE  01-01-2021            14-12-2021        15-01-2021   Fully Paid        15-02-2021    1302971     car        A1   36 months            Verified        83000.0  0.0231       106.53    0.0603         3500         28           3835

DataFrame Info:
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 38576 entries, 0 to 38575
Data columns (total 24 columns):
 #   Column                 Non-Null Count  Dtype  
---  ------                 --------------  -----  
 0   id                     38576 non-null  int64  
 1   address_state          38576 non-null  object 
 2   application_type       38576 non-null  object 
 3   emp_length             38576 non-null  object 
 4   emp_title              37138 non-null  object 
 5   grade                  38576 non-null  object 
 6   home_ownership         38576 non-null  object 
 7   issue_date             38576 non-null  object 
 8   last_credit_pull_date  38576 non-null  object 
 9   last_payment_date      38576 non-null  object 
 10  loan_status            38576 non-null  object 
 11  next_payment_date      38576 non-null  object 
 12  member_id              38576 non-null  int64  
 13  purpose                38576 non-null  object 
 14  sub_grade              38576 non-null  object 
 15  term                   38576 non-null  object 
 16  verification_status    38576 non-null  object 
 17  annual_income          38576 non-null  float64
 18  dti                    38576 non-null  float64
 19  installment            38576 non-null  float64
 20  int_rate               38576 non-null  float64
 21  loan_amount            38576 non-null  int64  
 22  total_acc              38576 non-null  int64  
 23  total_payment          38576 non-null  int64  
dtypes: float64(4), int64(5), object(15)
memory usage: 7.1+ MB

Descriptive Statistics:
                 id     member_id  annual_income           dti   installment      int_rate   loan_amount     total_acc  total_payment
count  3.857600e+04  3.857600e+04   3.857600e+04  38576.000000  38576.000000  38576.000000  38576.000000  38576.000000   38576.000000
mean   6.810371e+05  8.476515e+05   6.964454e+04      0.133274    326.862965      0.120488  11296.066855     22.132544   12263.348533
std    2.113246e+05  2.668105e+05   6.429368e+04      0.066662    209.092000      0.037164   7460.746022     11.392282    9051.104777
min    5.473400e+04  7.069900e+04   4.000000e+03      0.000000     15.690000      0.054200    500.000000      2.000000      34.000000
25%    5.135170e+05  6.629788e+05   4.150000e+04      0.082100    168.450000      0.093200   5500.000000     14.000000    5633.000000
50%    6.627280e+05  8.473565e+05   6.000000e+04      0.134200    283.045000      0.118600  10000.000000     20.000000   10042.000000
75%    8.365060e+05  1.045652e+06   8.320050e+04      0.185900    434.442500      0.145900  15000.000000     29.000000   16658.000000
max    1.077501e+06  1.314167e+06   6.000000e+06      0.299900   1305.190000      0.245900  35000.000000     90.000000   58564.000000

Missing Values per Column:
id                          0
address_state               0
application_type            0
emp_length                  0
emp_title                1438
grade                       0
home_ownership              0
issue_date                  0
last_credit_pull_date       0
last_payment_date           0
loan_status                 0
next_payment_date           0
member_id                   0
purpose                     0
sub_grade                   0
term                        0
verification_status         0
annual_income               0
dti                         0
installment                 0
int_rate                    0
loan_amount                 0
total_acc                   0
total_payment               0
dtype: int64

```

```python?code_reference&code_event_index=6
# Analyze key categorical columns

# Loan Purpose
print("Loan Purpose Distribution:")
print(df['purpose'].value_counts())

# Loan Status
print("\nLoan Status Distribution:")
print(df['loan_status'].value_counts())

# Home Ownership
print("\nHome Ownership Distribution:")
print(df['home_ownership'].value_counts())

# Loan Term
print("\nLoan Term Distribution:")
print(df['term'].value_counts())

# Loan Grade
print("\nLoan Grade Distribution:")
print(df['grade'].value_counts())

# Employment Length
print("\nEmployment Length Distribution:")
print(df['emp_length'].value_counts())
```

```text?code_stdout&code_event_index=6
Loan Purpose Distribution:
Debt consolidation    18214
credit card            4998
other                  3824
home improvement       2876
major purchase         2110
small business         1776
car                    1497
wedding                 928
medical                 667
moving                  559
house                   366
vacation                352
educational             315
renewable_energy         94
Name: purpose, dtype: int64

Loan Status Distribution:
Fully Paid     32145
Charged Off     5333
Current         1098
Name: loan_status, dtype: int64

Home Ownership Distribution:
RENT        18439
MORTGAGE    17198
OWN          2838
OTHER          98
NONE            3
Name: home_ownership, dtype: int64

Loan Term Distribution:
 36 months    28237
 60 months    10339
Name: term, dtype: int64

Loan Grade Distribution:
B    11674
A     9689
C     7904
D     5182
E     2786
F     1028
G      313
Name: grade, dtype: int64

Employment Length Distribution:
10+ years    8870
< 1 year     4575
2 years      4382
3 years      4088
4 years      3428
5 years      3273
1 year       3229
6 years      2228
7 years      1772
8 years      1476
9 years      1255
Name: emp_length, dtype: int64

```

Of course\! Here is a detailed overview of the financial loan dataset, suitable for a CV or a GitHub repository.

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
