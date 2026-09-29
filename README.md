🏦 Banking Analytics Dashboard

<img width="1257" height="652" alt="image" src="https://github.com/user-attachments/assets/cca8988f-37dc-4736-b28d-042277701152" />




An end-to-end banking analytics project using Power BI, Python, SQL, and Excel to analyze customers, loans, deposits, fees, account balances, and banking relationships.

📌 Project Overview

This project focuses on analyzing banking data and transforming it into meaningful business insights through data analysis, data preparation, KPI development, and interactive Power BI dashboards.

The project combines:

Python for Exploratory Data Analysis (EDA)

SQL for data querying and analysis

Power BI for interactive dashboards and visualization

DAX for calculated columns and business KPIs

Excel for source data and supporting analysis

The dashboard provides a consolidated view of customer activity, lending, deposits, account balances, fees, and customer engagement.

🎯 Problem Statement

The objective of this project is to develop an understanding of risk analytics in banking and financial services and demonstrate how banking data can be used to analyze customers and lending-related activities.

The dashboard helps users examine customer profiles, loan exposure, deposits, fees, banking relationships, and other financial metrics.

💡 Solution

An interactive Power BI dashboard was developed to provide a centralized view of important banking KPIs.

The dashboard enables analysis of:

Customer base

Total loan exposure

Bank loans

Business lending

Credit card balances

Total deposits

Savings accounts

Checking accounts

Foreign currency accounts

Processing fees

Customer engagement

Banking relationships

Customer demographics

🛠️ Tools & Technologies

Technology

Usage

Power BI

Dashboard development, visualization, data modeling and DAX

Python

Exploratory Data Analysis

Pandas

Data manipulation and analysis

NumPy

Numerical operations

Matplotlib

Data visualization

Seaborn

Statistical visualization

SQL

Data querying and analysis

Excel

Source data and supporting analysis

Jupyter Notebook

Python EDA

📊 Dashboard Pages

🏠 Home Dashboard

The Home page provides an executive-level overview of the banking portfolio.

It includes KPIs such as:

Total Clients

Total Loan

Total Deposit

Total Fees

Total Credit Card Amount

Savings Account Amount

The dashboard also includes filters for time period and gender, along with navigation to the Loan Analysis, Deposit Analysis, and Summary pages.



💰 Loan Analysis

The Loan Analysis page focuses on lending-related metrics.

It analyzes:

Total Loan

Bank Loan

Business Lending

Credit Cards

Bank Loan by Banking Relationship

Bank Loan by Income Band

Bank Loan by Nationality

Loan amounts by Engagement Timeframe

💵 Deposit Analysis

The Deposit Analysis page focuses on customer deposits and account balances.

It includes:

Total Deposit

Bank Deposit

Savings Account Amount

Checking Account Amount

Foreign Currency Amount

Deposit by Income Band

Deposit by Nationality

Deposit by Engagement Timeframe

📋 Summary Dashboard

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

🔎 Drill-Through Analysis

The project also includes a Drill Through page that allows users to move from aggregated dashboard views to more detailed customer-level analysis.

🧹 Data Preparation & Feature Engineering

Several calculated fields were created to improve the analysis.

Engagement Timeframe

Customers were categorized based on their engagement duration with the bank:

< 5 Years

< 10 Years

< 20 Years

> 20 Years

Engagement Days

The number of days since the customer joined the bank was calculated using DAX:

Engagment Days =
DATEDIFF(
    'Clients - Banking'[Joined Bank],
    TODAY(),
    DAY
)

Income Band

Estimated income was categorized into:

Low — less than 100,000

Mid — 100,000 to less than 300,000

High — 300,000 and above

Processing Fees

Processing fees were assigned according to the fee structure:

High → 5%

Mid → 3%

Low → 1%

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

Total Fees

Total Fees =
SUMX(
    'Clients - Banking',
    [Total Loan] * 'Clients - Banking'[Processing Fees]
)

Savings Account

Savings Account =
SUM('Clients - Banking'[Saving Accounts])

Checking Accounts

Checking Accounts =
SUM('Clients - Banking'[Checking Accounts])

Foreign Currency Account

Foreign Currency Account =
SUM('Clients - Banking'[Foreign Currency Account])

Credit Card Balance

Credit Cards Balance =
SUM('Clients - Banking'[Credit Card Balance])

🔎 Python Exploratory Data Analysis

The project includes a Jupyter Notebook for exploratory analysis using Python.

The EDA covers:

Data Understanding

Dataset shape

Data types

Descriptive statistics

Column inspection

Missing-value analysis

Customer-level analysis

Categorical Analysis

Banking relationship

Gender

Investment advisor

Nationality

Occupation

Fee structure

Loyalty classification

Income band

Numerical Analysis

Estimated income

Superannuation savings

Credit card balance

Bank loans

Bank deposits

Checking accounts

Savings accounts

Foreign currency accounts

Business lending

Visual Analysis

Bar charts

Count plots

Histograms

Distribution plots

Categorical comparisons

Correlation heatmap

📈 Key KPIs

KPI

Description

Total Clients

Number of distinct banking clients

Total Loan

Bank loan + business lending + credit card balance

Bank Loan

Total bank loan amount

Business Lending

Total business lending amount

Total Deposit

Combined deposit and account balances

Total Fees

Fees calculated from loan amounts and processing fee rates

Bank Deposit

Total bank deposit amount

Checking Account

Total checking account balance

Savings Account

Total savings account balance

Foreign Currency Account

Total foreign currency account balance

Credit Card Balance

Total credit card balance

Engagement Days

Number of days since the customer joined the bank

💼 Business Insights

The dashboard can be used to analyze:

Customer distribution across banking relationships

Loan exposure across income bands

Loan distribution across nationalities

Deposit distribution across customer segments

Customer engagement duration

Fee generation from lending activity

Account balance distribution

Relationships between different banking variables

These insights can support banking teams in understanding their customer base and financial portfolio.

📁 Repository Structure

Banking-Analytics-PowerBI-python-sql-AI/
│
├── Banking_Dashboard.pbix
├── Banking_Data.xlsx
├── Banking_Report.docx
├── Banking(1).csv
├── bank_EDA.ipynb
│
├── BANKING_DASHBOARD_HOME.png
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

Open it in Power BI Desktop.

Navigate through the Home, Loan Analysis, Deposit Analysis, and Summary pages.

Use the available filters and navigation buttons.

Use Drill Through for detailed analysis where available.

Python EDA

Open bank_EDA.ipynb.

Install the required Python libraries.

Load the banking dataset.

Run the notebook cells sequentially to reproduce the analysis.

Install the main libraries with:

pip install pandas numpy matplotlib seaborn

📄 Project Documentation

The repository includes Banking_Report.docx, which contains supporting documentation covering:

Problem statement

Dataset information

Data cleaning

Feature engineering

DAX functions

KPI definitions

Dashboard visualizations

Conclusion

Future work

🔮 Future Scope

This project can be extended with:

Customer segmentation

Credit risk scoring

Loan default prediction

Customer churn analysis

Time-series analysis

Predictive analytics

Automated reporting

Advanced customer-level risk analysis

👨‍💻 Author

Ravi Nandan

Senior Market Research Analyst | Data Analytics Enthusiast

Ravi Nandan is a Senior Market Research Analyst with an interest in data analytics, business intelligence, and data-driven decision-making. His work combines market research and analytical thinking with tools such as Power BI, SQL, Python, and Excel to transform data into structured business insights.

Connect with me

📧 Email: ravinandanyadavwork@gmail.com

💼 LinkedIn: linkedin.com/in/ravi-nandan-yadav-156a6a15a

💻 GitHub: github.com/ravi-nandan-data

⭐ Support the Project

If you found this project useful or informative, consider giving the repository a ⭐ Star on GitHub.

📌 Project Focus

Banking Analytics • Power BI • SQL • Python • Data Analysis • Business Intelligence
