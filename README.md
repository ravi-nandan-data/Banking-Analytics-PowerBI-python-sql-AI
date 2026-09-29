🏦 Banking Analytics Dashboard

<p align="center">
  <img src="BANKING_DASHBOARD_HOME.png" alt="Banking Analytics Dashboard" width="900"/>
</p>

<p align="center">
  <strong>End-to-end Banking Analytics project using Power BI, Python, SQL and Excel</strong>
</p>

<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python" alt="Python">
  </a>
  <a href="https://www.microsoft.com/en-us/power-platform/products/power-bi">
    <img src="https://img.shields.io/badge/Power%20BI-Data%20Visualization-F2C811?style=for-the-badge&logo=powerbi&logoColor=black" alt="Power BI">
  </a>
  <a href="https://www.sql.org/">
    <img src="https://img.shields.io/badge/SQL-Analysis-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="SQL">
  </a>
  <a href="https://pandas.pydata.org/">
    <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas" alt="Pandas">
  </a>
  <a href="https://numpy.org/">
    <img src="https://img.shields.io/badge/NumPy-Numerical%20Analysis-013243?style=for-the-badge&logo=numpy" alt="NumPy">
  </a>
  <a href="https://matplotlib.org/">
    <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge" alt="Matplotlib">
  </a>
  <a href="https://seaborn.pydata.org/">
    <img src="https://img.shields.io/badge/Seaborn-EDA-4C72B0?style=for-the-badge" alt="Seaborn">
  </a>
  <a href="https://jupyter.org/">
    <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter">
  </a>
  <a href="https://www.microsoft.com/en-us/microsoft-365/excel">
    <img src="https://img.shields.io/badge/Excel-Data-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white" alt="Excel">
  </a>
</p>

📊 Dashboard Preview

<p align="center">
  <img src="BANKING_DASHBOARD_HOME.png" alt="Banking Dashboard Home" width="900"/>
</p>

The dashboard provides an interactive view of banking customers, loans, deposits, fees, account balances, engagement, and customer characteristics.

📌 Project Overview

This project is a Banking Analytics Dashboard developed to analyze banking customers and financial activities using Power BI, Python, SQL, and Excel.

The project focuses on understanding banking data and converting it into meaningful business insights through:

Data preparation

Exploratory Data Analysis (EDA)

Feature engineering

SQL analysis

DAX measures

KPI development

Interactive dashboard design

Business-oriented visualization

The Power BI report contains dedicated pages for Home, Loan Analysis, Deposit Analysis, Summary, and Drill Through analysis.

🎯 Business Problem

Banking institutions manage large amounts of customer, lending, deposit, and account-level information.

The objective of this project is to provide a centralized analytical solution that helps users understand:

Customer distribution

Loan exposure

Deposit levels

Business lending

Credit card balances

Banking relationships

Customer engagement

Account balances

Fee generation

Customer characteristics by gender, nationality, income and other dimensions

The dashboard is designed to support data-driven banking and portfolio analysis.

💡 Project Solution

An interactive Power BI dashboard was developed to bring together important banking KPIs and analytical views.

The solution combines:

Raw Banking Data
       │
       ▼
Data Cleaning & Preparation
       │
       ▼
Python EDA + SQL Analysis
       │
       ▼
Feature Engineering
       │
       ▼
DAX Measures & KPIs
       │
       ▼
Power BI Data Model
       │
       ▼
Interactive Banking Dashboard
       │
       ▼
Business Insights

🛠️ Tech Stack

Technology

Purpose

🟨 Power BI

Interactive dashboards, data modeling, visualization and DAX

🐍 Python

Exploratory Data Analysis and data preparation

🗄️ SQL

Data querying and analytical operations

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

Purpose

Clients - Banking

Customer and banking-related information

Banking Relationship

Banking relationship information

Gender

Gender-related customer information

Investment Advisor

Investment advisor information

Period

Period/time-related information

The tables are connected through identifiers and relationships to support integrated analysis.

🧹 Data Cleaning & Feature Engineering

Several calculated fields were created in Power BI to make the raw banking data suitable for analysis.

⏳ Engagement Timeframe

Customers were categorized based on their engagement duration with the bank:

Category

< 5 Years

< 10 Years

< 20 Years

> 20 Years

📅 Engagement Days

The number of days since the customer joined the bank was calculated using DATEDIFF():

Engagment Days =
DATEDIFF(
    'Clients - Banking'[Joined Bank],
    TODAY(),
    DAY
)

💰 Income Band

Estimated income was grouped into three analytical categories:

Income

Band

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

💳 Total Credit Card Amount

Total CC Amount =
SUM('Clients - Banking'[Amount of Credit Cards])

💸 Total Fees

Total Fees =
SUMX(
    'Clients - Banking',
    [Total Loan] * 'Clients - Banking'[Processing Fees]
)

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

📊 Dashboard Pages

🏠 1. Home Dashboard

The Home page provides an executive overview of the banking portfolio.

Main KPIs

KPI

👥 Total Clients

💰 Total Loan

🏦 Total Deposit

💸 Total Fees

💳 Total CC Amount

💵 Savings Account Amount

The page also provides navigation to:

Loan Analysis

Deposit Analysis

Summary

💰 2. Loan Analysis

The Loan Analysis page focuses on lending activity.

Analysis Included

Total Loan

Bank Loan

Business Lending

Credit Cards

Bank Loan by Banking Relationship

Bank Loan by Income Band

Bank Loan by Nationality

Loan amounts by Engagement Timeframe

This page helps analyze how lending exposure is distributed across different customer segments.

💵 3. Deposit Analysis

The Deposit Analysis page focuses on deposits and account balances.

Analysis Included

Total Deposit

Bank Deposit

Savings Account Amount

Checking Account Amount

Foreign Currency Amount

Deposit by Income Band

Deposit by Nationality

Deposit by Engagement Timeframe

📋 4. Summary Dashboard

The Summary page consolidates the major banking KPIs into a single view.

KPIs Included

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

🔎 5. Drill-Through Analysis

The Power BI report includes a Drill Through page that allows users to move from summarized dashboard views toward more detailed customer-level analysis.

📈 Key Business KPIs

KPI

Description

👥 Total Clients

Number of distinct banking clients

💰 Total Loan

Bank loan + business lending + credit card balance

🏦 Bank Loan

Total bank loan amount

🏢 Business Lending

Total lending associated with businesses

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

The project includes a Jupyter Notebook for exploratory analysis using:

Pandas

NumPy

Matplotlib

Seaborn

EDA Areas

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

📈 Visualization

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

Different account balances

Relationships between banking variables

The project documentation also identifies customer, nationality, banking relationship and account-level analysis as important areas for understanding the banking portfolio.

🚀 How to Run the Project

Power BI Dashboard

Download Banking_Dashboard.pbix.

Open the file using Power BI Desktop.

Navigate through the dashboard pages.

Use the available filters and slicers.

Explore detailed information using Drill Through.

Python EDA

Open:

bank_EDA.ipynb

Install the main Python libraries:

pip install pandas numpy matplotlib seaborn

Then run the notebook cells sequentially.

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
├── 🖼️ HOME.png
├── 🖼️ LOAN ANALYSIS.png
├── 🖼️ DEPOSIT_ANALYSIS.png
├── 🖼️ SUMMARY.png
├── 🖼️ Drill Through.png
│
└── 📘 README.md

📚 Project Documentation

The repository contains a detailed project report covering:

Problem statement

Solution

Dataset

Data cleaning

Feature engineering

DAX functions

KPI definitions

Dashboard visualizations

Conclusion

Future work

🔮 Future Scope

The project can be further extended with:

Customer segmentation

Credit risk scoring

Loan default prediction

Customer churn analysis

Time-series analysis

Predictive analytics

Automated reporting

Advanced customer-level risk analysis

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

Business Queries

Analytical Calculations

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

📌 Learning Outcomes

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

Ravi Nandan is a Senior Market Research Analyst focused on market intelligence, strategic insights, and data-driven business analysis, with an interest in using analytics and visualization tools to solve business problems.

His analytical toolkit includes Power BI, SQL, Python, Excel, Pandas, and data visualization, with a focus on transforming raw data into structured insights and decision-support dashboards.

🔗 Connect With Me

📧 Email: ravinandanyadavwork@gmail.com

💼 LinkedIn: linkedin.com/in/ravi-nandan-yadav-156a6a15a

💻 GitHub: github.com/ravi-nandan-data

⭐ Support the Project

If you found this project useful, informative, or helpful for learning, consider giving the repository a ⭐ Star.
