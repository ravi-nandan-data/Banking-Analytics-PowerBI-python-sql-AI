📊 Banking Analytics Dashboard — Power BI, Python & SQL

<p align="center">











</p>

Dashboard Preview

<p align="center">



</p>

📈 Visualizations

The Power BI report includes:

Total Clients

Total Loan

Bank Loan

Business Lending

Total Deposit

Total Fees

Total Credit Card Amount

Savings Account Amount

Checking Account Amount

Foreign Currency Amount

Engagement Account

Bank Loan by Income Band

Bank Loan by Nationality

Deposit Analysis

Banking Relationship Analysis

Customer-level Drill Through

Executive Summary

📌 Project Overview

Banking institutions manage large amounts of customer and financial data related to loans, deposits, account balances, fees, and customer relationships.

This project performs an end-to-end banking analytics analysis using Power BI, Python, SQL, Pandas, NumPy, Matplotlib, Seaborn, and Excel to analyze banking customers, lending activity, deposits, account balances, and customer engagement.

The complete analytics workflow includes:

Data Preparation

Data Cleaning

Feature Engineering

Exploratory Data Analysis (EDA)

KPI Calculation

DAX Measure Development

Data Visualization

Banking Analysis

Business Insights

🎯 Business Problem

The objective of this project is to develop a basic understanding of risk analytics in banking and financial services and understand how data can be used to support lending-related decisions.

The dashboard provides a consolidated view of customer and banking information to help analyze:

Customer profiles

Loan exposure

Business lending

Credit card balances

Deposits

Account balances

Banking relationships

Customer engagement

Fees generated from lending activity

Business Objective

Develop a data-driven banking dashboard to:

Analyze the total number of banking clients

Understand total loan exposure

Analyze bank loans and business lending

Analyze customer deposits and account balances

Compare banking metrics across customer segments

Analyze customer engagement with the bank

Understand fee generation from lending activity

Provide a consolidated view of important banking KPIs

📂 Dataset

The project dataset contains banking and customer information organized across multiple related tables.

Main Tables

Table

Clients - Banking

Banking Relationship

Gender

Investment Advisor

Period

The tables are interconnected using keys such as primary keys and foreign keys.

Key Data Categories

The dataset contains information related to:

Client ID

Joined Bank Date

Banking Relationship

Gender

Nationality

Investment Advisor

Estimated Income

Fee Structure

Loyalty Classification

Bank Loans

Business Lending

Credit Card Balance

Bank Deposits

Savings Accounts

Checking Accounts

Foreign Currency Account

Amount of Credit Cards

🏗 Tech Stack

Power BI

Python

SQL

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

Excel

🔄 Project Workflow

Banking Dataset
      │
      ▼
Data Preparation
      │
      ▼
Data Cleaning
      │
      ▼
Feature Engineering
      │
      ▼
Exploratory Data Analysis
      │
      ▼
DAX & KPI Development
      │
      ▼
Power BI Visualization
      │
      ▼
Banking Analysis
      │
      ▼
Business Insights

🧹 Data Cleaning

The following data preparation and feature engineering steps were performed:

Created an Engagement Timeframe column

Created an Engagement Days column

Created Income Band categories

Created a Processing Fees column based on fee structure

Prepared the banking data for KPI and dashboard analysis

Used calculated columns and DAX measures for analysis

⚙ Feature Engineering

Several business-ready features were created in Power BI.

1. Engagement Timeframe

Customers were categorized according to their engagement period with the bank:

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

Estimated income was categorized into:

Low — less than 100,000

Mid — less than 300,000

High — 300,000 and above

4. Processing Fees

Processing fees were assigned according to the fee structure:

Fee Structure

Processing Fee

High

5%

Mid

3%

Low

1%

📈 Key Business KPIs

KPI

Description

Total Clients

Total number of distinct banking clients

Total Loan

Bank Loan + Business Lending + Credit Card Balance

Bank Loan

Total bank loan amount

Business Lending

Total amount of business lending

Total Deposit

Bank Deposit + Savings + Foreign Currency + Checking Accounts

Total Fees

Fees calculated from loan amounts and processing fee rates

Bank Deposit

Total bank deposits

Checking Account Amount

Total checking account balance

Total CC Amount

Total credit card amount

Saving Account Amount

Total savings account balance

Foreign Currency Amount

Total foreign currency account amount

Engagement Account

Engagement duration represented through engagement days

📐 DAX Measures

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

📊 Dashboard

1. Home Dashboard

The Home dashboard provides an overall view of the banking portfolio.

It includes:

Total Clients

Total Loan

Total Deposit

Total Fees

Total Credit Card Amount

Savings Account Amount

Navigation is provided for:

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

Loan amounts by Engagement Timeframe



3. Deposit Analysis

The Deposit Analysis page focuses on deposits and account balances.

It includes:

Total Deposit

Bank Deposit

Foreign Currency Amount

Savings Account Amount

Checking Account Amount

Deposit by Income Band

Deposit by Nationality

Deposit by Engagement Timeframe



4. Summary Dashboard

The Summary dashboard provides a consolidated view of major banking KPIs.

It includes:

Total Clients

Total Loan

Bank Loan

Business Lending

Total Deposit

Total Fees

Bank Deposit

Checking Account Amount

Total CC Amount

Savings Account Amount

Foreign Currency Amount

Engagement Account



5. Drill Through

The report also includes a Drill Through page for moving from summarized dashboard analysis toward detailed customer-level information.



🔍 Key Insights

The dashboard can be used to analyze:

The distribution of customers across banking relationships

Loan exposure across different income bands

Bank loan distribution by nationality

Deposit distribution across customer segments

Different types of customer account balances

Customer engagement duration

Fee generation from lending activity

Credit card balances

Relationships between banking and customer-level variables

The project documentation also identifies differences in client distribution across banking relationships and provides analysis of loan distribution by nationality.

💡 Business Recommendations

Based on the analysis available in the project, banks can use the dashboard to:

Monitor customer and loan portfolios

Analyze loan exposure across customer segments

Compare banking relationships

Monitor deposit and account balances

Identify customer segments with different engagement durations

Analyze lending-related fee generation

Use nationality and income-band analysis to support portfolio strategy

Develop more detailed customer-level risk analysis in future versions

📁 Project Structure

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

Power BI Dashboard

Download Banking_Dashboard.pbix.

Open the file using Power BI Desktop.

Start from the Home page.

Use the navigation buttons to open Loan Analysis, Deposit Analysis, and Summary.

Apply available filters and slicers.

Use Drill Through for detailed analysis where available.

Python EDA

Open bank_EDA.ipynb.

Load the banking dataset.

Run the notebook cells sequentially.

Perform data exploration and visualization using Python libraries.

🧠 Skills Demonstrated

Data Analytics

Data Cleaning

Data Transformation

Feature Engineering

Exploratory Data Analysis

KPI Development

Business Analysis

Power BI

Dashboard Development

Data Modeling

DAX Measures

KPI Cards

Interactive Visualizations

Slicers

Drill Through

Dashboard Navigation

Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

SQL

Data Querying

Data Aggregation

Banking Data Analysis

Business Analytics

Banking Analytics

Loan Analysis

Deposit Analysis

Customer Analysis

Financial KPI Analysis

Risk Analytics

📚 Learning Outcomes

Through this project I learned how to:

Analyze banking and customer datasets

Perform exploratory data analysis using Python

Create calculated columns using DAX

Build business KPIs in Power BI

Design interactive banking dashboards

Analyze loans and deposits

Analyze customer engagement

Translate banking data into business-oriented visualizations

Present financial metrics through an interactive dashboard

📌 Key Takeaways

✔ Built an end-to-end banking analytics project

✔ Created an interactive Power BI banking dashboard

✔ Performed exploratory data analysis using Python

✔ Created calculated columns and DAX measures

✔ Analyzed loans, deposits, fees, and account balances

✔ Developed customer and banking relationship analysis

✔ Created multiple dashboard pages with interactive navigation

✔ Added Drill Through functionality for detailed analysis

📷 Project Files

📊 Power BI Dashboard

📓 Python EDA Notebook

🗄 Banking Dataset

📑 Banking Project Report

📈 Dashboard Screenshots

📋 README Documentation

👨‍💻 Author

Ravi Nandan Yadav

Market Research Analyst | Data Analytics Enthusiast

📧 Email: ravinandanyadavwork@gmail.com

💼 LinkedIn: https://www.linkedin.com/in/ravi-nandan-yadav-156a6a15a/

💻 GitHub: https://github.com/ravi-nandan-data/Banking-Analytics-PowerBI-python-sql-AI


⭐ If you found this project useful, consider giving it a Star!
