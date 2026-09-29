🏦 Banking Analytics Dashboard

<p align="center">
  <img src="BANKING_DASHBOARD_HOME.png" alt="Banking Analytics Dashboard" width="900">
</p>

<p align="center">
  <strong>Banking Analytics using Power BI, Python, SQL & Excel</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI-Data%20Visualization-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" alt="Power BI">
  <img src="https://img.shields.io/badge/Python-Data%20Analysis-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/SQL-Analysis-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Analysis-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge" alt="Matplotlib">
  <img src="https://img.shields.io/badge/Seaborn-EDA-4C72B0?style=for-the-badge" alt="Seaborn">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Excel-Data-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white" alt="Excel">
</p>

📊 Dashboard Preview

The banking dashboard provides an interactive overview of customers, loans, deposits, fees, account balances, gender, and engagement.

<p align="center">
  <img src="BANKING_DASHBOARD_HOME.png" alt="Banking Dashboard Home" width="900">
</p>

📈 Visualizations

The Power BI report includes multiple analytical pages and interactive views:

👥 Total Clients

💰 Total Loan

🏦 Total Deposit

💸 Total Fees

💳 Credit Card Amount

💵 Savings Account Amount

🏦 Bank Loan Analysis

🏢 Business Lending Analysis

🌍 Loan by Nationality

💼 Loan by Income Band

🤝 Banking Relationship Analysis

⏳ Engagement Timeframe Analysis

📊 Deposit Analysis

🔎 Drill-Through Analysis

📋 Executive Summary

📌 Project Overview

This project is an end-to-end Banking Analytics project developed to analyze customer and financial data and convert it into meaningful business insights.

The project combines Power BI, Python, SQL, and Excel to perform data preparation, exploratory analysis, KPI development, DAX calculations, and interactive dashboard reporting.

The analysis focuses on:

Customer analysis

Loan portfolio analysis

Deposit analysis

Business lending

Credit card balances

Banking relationships

Customer engagement

Account balances

Processing fees

Customer demographics

🎯 Business Problem

Banking institutions manage large volumes of customer and financial information. Without a centralized analytical view, it can be difficult to understand customer behavior, lending exposure, deposits, and account-level activity.

Business Objective

The objective of this project is to build an interactive analytical solution that helps users:

Understand the customer base

Analyze total loan exposure

Compare bank loans and business lending

Analyze deposits across account types

Understand customer engagement

Compare banking relationships

Analyze loan distribution by nationality and income band

Monitor important banking KPIs

💡 Project Solution

A Power BI dashboard was developed to provide an interactive and centralized view of banking performance.

The complete workflow is:

Banking Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Feature Engineering
      │
      ▼
Python EDA + SQL Analysis
      │
      ▼
DAX Measures & KPIs
      │
      ▼
Power BI Data Model
      │
      ▼
Interactive Dashboard
      │
      ▼
Business Insights

🛠️ Tech Stack

Technology

Purpose

🟨 Power BI

Dashboard development, data modeling, DAX and visualization

🐍 Python

Exploratory Data Analysis and data preparation

🗄️ SQL

Data querying and analysis

🐼 Pandas

Data manipulation and analysis

🔢 NumPy

Numerical operations

📊 Matplotlib

Data visualization

📈 Seaborn

Statistical visualization

📓 Jupyter Notebook

Python-based EDA

📗 Excel

Source data and supporting analysis

📂 Dataset

The project documentation describes a banking dataset containing multiple related tables.

Main Tables

Table

Description

Clients - Banking

Customer and banking-related information

Banking Relationship

Banking relationship information

Gender

Gender-related customer information

Investment Advisor

Investment advisor information

Period

Period-related information

The tables are connected through identifiers and relationships to support integrated banking analysis.

🧹 Data Cleaning & Feature Engineering

Several calculated fields were created to make the raw banking data suitable for analysis.

⏳ Engagement Timeframe

Customers were categorized according to their engagement duration:

Category

< 5 Years

< 10 Years

< 20 Years

> 20 Years

📅 Engagement Days

The number of days since a customer joined the bank was calculated using DATEDIFF().

Engagment Days =
DATEDIFF(
    'Clients - Banking'[Joined Bank],
    TODAY(),
    DAY
)

💰 Income Band

Estimated income was grouped into three categories:

Estimated Income

Income Band

< 100,000

Low

100,000 – < 300,000

Mid

≥ 300,000

High

💳 Processing Fees

Processing fees were assigned according to the fee structure:

Fee Structure

Processing Fee

High

5%

Mid

3%

Low

1%

📐 Key DAX Measures

👥 Total Clients

Total Clients =
DISTINCTCOUNT('Clients - Banking'[Client ID])

💰 Bank Loan

Bank Loan =
SUM('Clients - Banking'[Bank Loans])

🏢 Business Lending

Business Lending =
SUM('Clients - Banking'[Business Lending])

💵 Total Loan

Total Loan =
[Bank Loan] +
[Business Lending] +
[Credit Cards Balance]

🏦 Bank Deposit

Bank Deposit =
SUM('Clients - Banking'[Bank Deposits])

💰 Total Deposit

Total Deposit =
[Bank Deposit] +
[Savings Account] +
[Foreign Currency Account] +
[Checking Accounts]

💸 Total Fees

Total Fees =
SUMX(
    'Clients - Banking',
    [Total Loan] * 'Clients - Banking'[Processing Fees]
)

💳 Total Credit Card Amount

Total CC Amount =
SUM('Clients - Banking'[Amount of Credit Cards])

💰 Savings Account

Savings Account =
SUM('Clients - Banking'[Saving Accounts])

💳 Checking Accounts

Checking Accounts =
SUM('Clients - Banking'[Checking Accounts])

🌍 Foreign Currency Account

Foreign Currency Account =
SUM('Clients - Banking'[Foreign Currency Account])

💳 Credit Card Balance

Credit Cards Balance =
SUM('Clients - Banking'[Credit Card Balance])

🏠 Dashboard Pages

1. 🏠 Home Dashboard

The Home page provides an executive-level overview of the banking portfolio.

Key KPIs include:

KPI

👥 Total Clients

💰 Total Loan

💵 Total Deposit

💸 Total Fees

💳 Total CC Amount

💰 Savings Account Amount

<p align="center">
  <img src="BANKING_HOME.png" alt="Home Dashboard" width="900">
</p>

2. 💰 Loan Analysis

The Loan Analysis page focuses on lending-related activity.

It includes:

Total Loan

Bank Loan

Business Lending

Credit Cards

Bank Loan by Banking Relationship

Bank Loan by Income Band

Bank Loan by Nationality

Loan amounts by Engagement Timeframe

<p align="center">
  <img src="BANKING_LOAN_ANALYSIS.png" alt="Loan Analysis Dashboard" width="900">
</p>

3. 💵 Deposit Analysis

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

4. 📋 Summary Dashboard

The Summary page provides a consolidated view of the major banking KPIs.

It includes:

Category

KPI

👥 Customers

Total Clients

💰 Lending

Total Loan

🏦 Lending

Bank Loan

🏢 Lending

Business Lending

💵 Deposits

Total Deposit

💸 Revenue

Total Fees

🏦 Deposits

Bank Deposit

💳 Accounts

Checking Account Amount

💳 Credit

Total CC Amount

💰 Accounts

Savings Account Amount

🌍 Accounts

Foreign Currency Amount

🤝 Engagement

Engagement Account

<p align="center">
  <img src="BANKING_SUMMARY.png" alt="Summary Dashboard" width="900">
</p>

5. 🔎 Drill-Through Analysis

The report includes a Drill Through page that allows users to move from aggregated dashboard analysis toward more detailed customer-level information.

<p align="center">
  <img src="BANKING_DRILL_THROUGH.png" alt="Drill Through Dashboard" width="900">
</p>

📊 Key Business KPIs

KPI

Description

👥 Total Clients

Number of distinct banking clients

💰 Total Loan

Bank loan + business lending + credit card balance

🏦 Bank Loan

Total bank loan amount

🏢 Business Lending

Total business lending amount

💵 Total Deposit

Combined bank, savings, checking and foreign currency amounts

💸 Total Fees

Fees calculated from loan amounts and processing fee rates

🏦 Bank Deposit

Total amount deposited in bank accounts

💳 Checking Account

Total checking account balance

💰 Savings Account

Total savings account balance

🌍 Foreign Currency Account

Total foreign currency account balance

💳 Credit Card Balance

Total credit card balance

⏳ Engagement Days

Number of days since the customer joined the bank

🐍 Python Exploratory Data Analysis

The project includes a Jupyter Notebook for exploratory analysis using Python, Pandas, NumPy, Matplotlib and Seaborn.

🔍 Data Understanding

Dataset inspection

Data types

Descriptive statistics

Column analysis

Data quality checks

📊 Categorical Analysis

Banking relationship

Gender

Investment advisor

Nationality

Occupation

Fee structure

Loyalty classification

Income band

🔢 Numerical Analysis

Estimated income

Superannuation savings

Credit card balance

Bank loans

Bank deposits

Checking accounts

Savings accounts

Foreign currency accounts

Business lending

📈 Visual Analysis

Bar charts

Count plots

Histograms

Distribution analysis

Categorical comparisons

Correlation heatmap

🔍 Business Insights

The dashboard enables analysis of:

Customer distribution across banking relationships

Loan exposure across income bands

Loan distribution across nationalities

Deposit distribution across customer segments

Customer engagement duration

Fee generation from lending activity

Account balance distribution

Relationships between banking variables

The project documentation also highlights customer, nationality, banking relationship and account-level analysis as important areas for understanding the banking portfolio.

🚀 How to Use the Project

Power BI

Download Banking_Dashboard.pbix.

Open the file using Power BI Desktop.

Navigate through the Home, Loan Analysis, Deposit Analysis and Summary pages.

Use available filters and slicers.

Use Drill Through for detailed analysis.

Python EDA

Open:

bank_EDA.ipynb

Install the main libraries:

pip install pandas numpy matplotlib seaborn

Run the notebook cells sequentially to reproduce the EDA.

📁 Repository Structure

Banking-Analytics-PowerBI-python-sql-AI/
│
├── 📊 Banking_Dashboard.pbix
├── 📗 Banking_Data.xlsx
├── 📄 Banking_Report.docx
├── 📄 Banking(1).csv
├── 📓 bank_EDA.ipynb
│
├── 🖼️ BANKING_DASHBOARD_HOME.png
├── 🖼️ BANKING_HOME.png
├── 🖼️ BANKING_LOAN_ANALYSIS.png
├── 🖼️ BANKING_SUMMARY.png
├── 🖼️ BANKING_DRILL_THROUGH.png
│
└── 📘 README.md

🎓 Skills Demonstrated

📊 Data Analytics

Data Cleaning

Data Transformation

Feature Engineering

Exploratory Data Analysis

KPI Development

🗄️ SQL

Data Extraction

Joins

Aggregations

Analytical Queries

Business Calculations

🐍 Python

Pandas

NumPy

Matplotlib

Seaborn

Jupyter Notebook

📈 Power BI

Data Modeling

DAX

KPI Cards

Interactive Visualizations

Slicers

Drill Through

Dashboard Navigation

💼 Business Analytics

Banking Portfolio Analysis

Customer Analysis

Loan Analysis

Deposit Analysis

Fee Analysis

Business Reporting

Data Storytelling

📚 Learning Outcomes

Through this project, I worked on:

Building an end-to-end banking analytics workflow

Preparing and analyzing banking data

Creating business-focused KPIs

Developing DAX measures

Performing exploratory data analysis

Designing interactive Power BI dashboards

Translating banking data into business-oriented insights

👨‍💻 Author

Ravi Nandan

Senior Market Research Analyst | Data Analytics Enthusiast

Ravi Nandan is a Senior Market Research Analyst focused on market intelligence, strategic insights and data-driven business analysis, with an interest in using analytics and visualization tools to solve business problems.

His analytical toolkit includes Power BI, SQL, Python, Excel, Pandas and data visualization, with a focus on transforming raw data into structured insights and decision-support dashboards.

🔗 Connect With Me

📧 Email: ravinandanyadavwork@gmail.com

💼 LinkedIn: linkedin.com/in/ravi-nandan-yadav-156a6a15a

💻 GitHub: github.com/ravi-nandan-data

⭐ Support the Project

If you found this project useful, consider giving the repository a ⭐ Star.
