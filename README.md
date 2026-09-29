Banking Analytics Dashboard — Power BI, Python & SQL

📌 Project Overview

This project is a Banking Analytics Dashboard developed to analyze banking customers, loans, deposits, fees, account balances, and customer relationships.

The project combines Python, SQL, and Power BI to perform exploratory data analysis, data preparation, KPI calculation, and interactive dashboard development.

The main objective is to use banking data to support analysis of customer profiles, lending activity, deposits, account balances, and other banking-related metrics.

🎯 Problem Statement

The project focuses on developing an understanding of risk analytics in banking and financial services and how data can be used to support better lending-related decisions.

The Power BI dashboards provide a consolidated view of customer and banking information, allowing users to analyze loan amounts, deposits, customer characteristics, banking relationships, and other financial metrics.

💡 Solution

An interactive Power BI dashboard was created to provide a centralized view of key banking KPIs and customer-level information.

The dashboard allows users to:

Monitor total clients

Analyze total loan exposure

Compare bank loans and business lending

Analyze credit card balances

Analyze total deposits and different account types

Analyze banking relationships

Compare customers by nationality, gender, income band, and engagement timeframe

Analyze fees generated from lending activity

Explore customer-level information using drill-through functionality

🛠️ Tools & Technologies

Tool / Technology

Purpose

Power BI

Dashboard development, data modeling, DAX measures, interactive visualization

Python

Exploratory Data Analysis and statistical/visual analysis

Pandas

Data manipulation and analysis

NumPy

Numerical operations

Matplotlib

Data visualization

Seaborn

Statistical visualization

PostgreSQL

Database connectivity and SQL-based data extraction

SQL

Querying banking/customer data

Excel

Source dataset and supporting tables

Jupyter Notebook

Python-based EDA

📂 Dataset

The project dataset contains banking and customer information organized across multiple related tables.

Main Tables

Clients - Banking

Gender

Banking Relationship

Investment Advisor

The tables are connected through identifiers such as client IDs and other key fields.

The main customer-banking dataset contains approximately 2,999 records and 25 fields.

Key Data Categories

The dataset includes information related to:

Client ID

Client name

Age

Joined bank date

Investment advisor

Nationality

Occupation

Fee structure

Loyalty classification

Estimated income

Superannuation savings

Credit card balance

Bank loans

Bank deposits

Checking accounts

Savings accounts

Foreign currency accounts

Business lending

Banking relationship

Gender

🧹 Data Preparation & Feature Engineering

Several calculated columns were created in Power BI for analysis.

1. Engagement Timeframe

A customer engagement category was created to classify how long customers have been associated with the bank.

Categories include:

< 5 Years

< 10 Years

< 20 Years

> 20 Years

2. Engagement Days

The number of days since the customer joined the bank was calculated using DATEDIFF().

Engagment Days =
DATEDIFF(
    'Clients - Banking'[Joined Bank],
    TODAY(),
    DAY
)

3. Income Band

Estimated income was categorized into three groups:

Low: less than 100,000

Medium: 100,000 to less than 300,000

High: 300,000 and above

The Python EDA also uses the same income-band concept with pandas.cut().

4. Processing Fees

Processing fees were assigned according to the fee structure:

High → 5%

Medium → 3%

Low → 1%

📊 Power BI Dashboard

The Power BI report contains multiple interactive pages.

1. Home Dashboard

The Home page provides a high-level overview of the banking portfolio.

Key KPIs include:

Total Clients

Total Loan

Total Deposit

Total Fees

Total Credit Card Amount

Savings Account Amount

Navigation buttons are provided for:

Loan Analysis

Deposit Analysis

Summary



2. Loan Analysis

The Loan Analysis page focuses on lending-related metrics.

It includes:

Total Loan

Bank Loan

Business Lending

Credit Cards

Bank Loan by Banking Relationship

Bank Loan by Income Band

Bank Loan by Nationality

Loan amounts by engagement timeframe



3. Deposit Analysis

The Deposit Analysis page focuses on customer deposits and account balances.

It includes analysis of:

Total Deposit

Bank Deposit

Savings Account

Checking Account

Foreign Currency Account

Deposit by Income Band

Deposit by Nationality

Deposit by Engagement Timeframe



4. Summary Dashboard

The Summary page provides a consolidated view of the major banking KPIs.

It includes:

Total Clients

Total Loan

Bank Loan

Business Lending

Total Deposit

Total Fees

Bank Deposit

Checking Account Amount

Total Credit Card Amount

Savings Account Amount

Foreign Currency Amount

Engagement Account



5. Drill-Through

The report also includes a Drill Through page to allow users to move from aggregated dashboard analysis toward more detailed customer-level information.



📐 Key DAX Measures

Total Clients

Total Clients =
DISTINCTCOUNT('Clients - Banking'[Client ID])

Bank Loan

Bank Loan =
SUM('Clients - Banking'[Bank Loans])

Business Lending

Business Lending =
SUM('Clients - Banking'[Business Lending])

Total Loan

Total Loan =
[Bank Loan] +
[Business Lending] +
[Credit Cards Balance]

Bank Deposit

Bank Deposit =
SUM('Clients - Banking'[Bank Deposits])

Total Deposit

Total Deposit =
[Bank Deposit] +
[Savings Account] +
[Foreign Currency Account] +
[Checking Accounts]

Total Credit Card Amount

Total CC Amount =
SUM('Clients - Banking'[Amount of Credit Cards])

Savings Account

Savings Account =
SUM('Clients - Banking'[Saving Accounts])

Checking Accounts

Checking Accounts =
SUM('Clients - Banking'[Checking Accounts])

Foreign Currency Account

Foreign Currency Account =
SUM('Clients - Banking'[Foreign Currency Account])

Total Fees

Total Fees =
SUMX(
    'Clients - Banking',
    [Total Loan] * 'Clients - Banking'[Processing Fees]
)

🔎 Python EDA

Exploratory Data Analysis was performed using Python, Pandas, Matplotlib, and Seaborn.

The EDA includes:

Data Inspection

Dataset shape

Data types

Descriptive statistics

Column inspection

Individual customer-level filtering

Categorical Analysis

The analysis covers variables such as:

Banking relationship

Gender

Investment advisor

Nationality

Occupation

Fee structure

Loyalty classification

Properties owned

Risk weighting

Income band

Numerical Analysis

Numerical variables analyzed include:

Estimated income

Superannuation savings

Credit card balance

Bank loans

Bank deposits

Checking accounts

Savings accounts

Foreign currency account

Business lending

Visual Analysis

The notebook includes:

Bar charts

Count plots

Histograms

KDE-based distributions

Categorical comparisons

Correlation heatmap

Correlation Analysis

A correlation matrix was created for the major numerical banking variables.

The EDA documentation notes positive relationships between bank deposits, checking accounts, savings accounts, and foreign currency accounts, indicating that customers with higher balances in one account category may also maintain substantial balances across other account types.

📈 Key Business Metrics

The dashboard focuses on the following banking metrics:

Metric

Description

Total Clients

Number of distinct banking clients

Total Loan

Bank loan + business lending + credit card balance

Bank Loan

Total bank loan amount

Business Lending

Lending amount associated with businesses

Total Deposit

Combined bank, savings, checking, and foreign currency deposits

Total Fees

Fees calculated from loan amounts and processing fee rates

Bank Deposit

Total amount deposited in bank accounts

Checking Account

Total checking account balance

Savings Account

Total savings account balance

Foreign Currency Account

Total foreign currency account balance

Credit Card Balance

Total credit card balance

Engagement Days

Number of days since customers joined the bank

📌 Business Insights

The project enables analysis of:

Customer distribution across different banking relationships

Loan exposure across income bands

Loan distribution across nationalities

Deposit distribution across customer segments

Customer engagement duration

Fee generation from lending activity

Distribution of different account balances

Relationships between banking variables

The project documentation also highlights the use of customer, nationality, banking relationship, and account-level information to support banking strategy and portfolio analysis.

📁 Repository Structure

Banking-Analytics-PowerBI-python-sql-AI/
│
├── Banking_Dashboard.pbix
├── Banking_Data.xlsx
├── Banking_Report.docx
├── Banking(1).csv
├── bank_EDA.ipynb
│
├── HOME.png
├── LOAN ANALYSIS.png
├── DEPOSIT_ANALYSIS.png
├── SUMMARY.png
├── Drill Through.png
│
└── README.md

🚀 How to Use

Power BI

Download Banking_Dashboard.pbix.

Open the file using Power BI Desktop.

Review the Home, Loan Analysis, Deposit Analysis, and Summary pages.

Use the available slicers and navigation buttons to interact with the dashboard.

Use Drill Through where applicable for detailed analysis.

Python EDA

Open bank_EDA.ipynb.

Install the required Python libraries.

Connect to the PostgreSQL database if reproducing the SQL workflow.

Load the customer banking data.

Run the notebook cells sequentially to reproduce the EDA.

Example libraries:

pip install pandas numpy matplotlib seaborn psycopg2-binary sqlalchemy

📄 Project Documentation

The repository also contains Banking_Report.docx, which documents:

Problem statement

Dataset structure

Data cleaning

Calculated columns

DAX functions

KPI definitions

Dashboard visualizations

Conclusion

Future work

🔮 Future Scope

The project can be extended by adding:

Customer segmentation

Loan default prediction

Credit risk scoring

Customer churn analysis

Time-series analysis

Automated reporting

Advanced predictive models

Additional SQL-based analytics

More granular customer-level risk analysis

👤 Author

Ravi Nandan Yadav

Focus: Data Analytics | Power BI | SQL | Python | Banking Analytics

⭐ Project Summary

This project demonstrates an end-to-end banking analytics workflow combining:

SQL → Python EDA → Data Preparation → DAX → Power BI → Interactive Banking Dashboard

It showcases practical skills in data analysis, visualization, KPI development, business-oriented reporting, and banking analytics.

👨‍💻 Author
Ravi Nandan

Senior Market Research Analyst | Data Analytics Enthusiast

📧 Email: ravinandanyadavwork@gmail.com

💼 LinkedIn: https://www.linkedin.com/in/ravi-nandan-yadav-156a6a15a/

💻 GitHub: https://github.com/yourusername

⭐ If you found this project useful, consider giving it a Star!
