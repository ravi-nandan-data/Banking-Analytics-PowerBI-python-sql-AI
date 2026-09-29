🏦 Banking Analytics Dashboard

An end-to-end banking analytics project using Excel, PostgreSQL, Python and Power BI

Show Image Show Image Show Image Show Image

</div>
📑 Table of Contents
Problem Statement
Solution
Dashboard Preview
About the Dataset
Data Cleaning & Feature Engineering
KPIs and DAX Measures
Exploratory Data Analysis (Python)
Tech Stack
Project Structure
How to Run
Author
🎯 Problem Statement

Develop a basic understanding of risk analytics in banking and financial services, and understand how data is used to minimise the risk of losing money while lending to customers.

💡 Solution

Interactive dashboards built with the latest Power BI tools help the bank make decisions based on the applicant's profile. If the applicant is likely to repay the loan, the loan is approved; otherwise it is not.

The dashboards let users analyse loans, deposits and fees by banking relationship, gender, investment advisor, income band, nationality and client engagement timeframe.

📊 Dashboard Preview
🏠 Home

Landing page with navigation buttons, joining-year and gender slicers, and headline KPIs: Total Clients, Total Loan, Total Deposit, Total Fees, Total CC Amount and Saving Account Amount.

Show Image

💳 Loan Analysis

Total Loan, Bank Loan, Business Lending and Credit Cards, with bank loan split by banking relationship, income band and nationality, and loan components by engagement timeframe.

Show Image

💰 Deposit Analysis

Total Deposit, Bank Deposit, Foreign Currency, Saving and Checking account amounts, with deposits by income band, nationality and engagement timeframe.

Show Image

📋 Summary

A single-page view of all key metrics: deposits, loans, business lending, credit cards, fees, accounts, clients and engagement.

Show Image

🔍 Drill Through – Fees

Total Fees by loyalty classification, and by engagement length and nationality.

Show Image

🗂 About the Dataset

The dataset contains bank and client details across multiple tables, linked to each other through primary and foreign keys.

Table	Description
Clients – Banking	Main fact table with client details, income, loans, deposits, credit cards and fee structure (about 3,000 client records)
Banking Relationship	Relationship type (for example, Retail, Institutional)
Gender	Gender lookup
Investment Advisor	Investment advisor lookup
Period	Date and period table

Source file: data/Banking_Data.xlsx

🧹 Data Cleaning & Feature Engineering
New Column	Table	Purpose
Engagement Timeframe	Clients – Banking	Shows the timeline of the client's relationship with the bank
Engagement Days	Clients – Banking	Number of days since the client joined the bank
Income Band	Clients – Banking	Estimated income below 100,000 = Low, below 300,000 = Mid, otherwise High
Processing Fees	Clients – Banking	Derived from Fee Structure (for example, a High fee structure gives a processing fee of 0.05)
📐 KPIs and DAX Measures
KPI	Description	DAX
Total Clients	Total number of clients	DISTINCTCOUNT('Clients - Banking'[Client ID])
Bank Loan	Loan amount to be repaid by clients	SUM('Clients - Banking'[Bank Loans])
Business Lending	Loan amount given to small businesses	SUM('Clients - Banking'[Business Lending])
Total Loan	Bank loan + business lending + credit card balance	[Bank Loan] + [Business Lending] + [Credit Cards Balance]
Bank Deposit	Money deposited in the bank	SUM('Clients - Banking'[Bank Deposits])
Checking Account Amount	Accounts for daily transactional needs	SUM('Clients - Banking'[Checking Accounts])
Total CC Amount	Total credit card amount	SUM('Clients - Banking'[Amount of Credit Cards])
Total Deposit	Bank deposit + savings + foreign currency + checking	[Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]
Total Fees	Amount charged for account set-up, maintenance and so on	SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])
DAX functions used
Function	Use
SUM	Adds all numbers in a column
DISTINCTCOUNT	Counts distinct values in a column
SUMX	Sums an expression evaluated row by row
SWITCH	Returns a result based on a list of conditions
DATEDIFF	Number of intervals between two dates, for example DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
🐍 Exploratory Data Analysis (Python)

The notebook notebooks/bank_EDA.ipynb loads the data from PostgreSQL (customer_data table) into pandas and performs:

Data inspection: head, shape, info, describe
Income band creation with pd.cut()
Univariate and bivariate analysis of categorical columns (banking relationship, gender, advisor, nationality, occupation, fee structure, loyalty classification, risk weighting and more)
Distribution analysis of numerical columns (income, savings, loans, deposits, and so on)
Correlation heatmap

Key insight: The strongest positive correlation is between Bank Deposits and Checking, Saving and Foreign Currency accounts. This shows that clients who hold high balances in one account type often hold substantial funds across other accounts too.

🛠 Tech Stack
Category	Tools
Data visualization	Power BI, DAX
Database	PostgreSQL
Programming	Python (pandas, NumPy, Matplotlib, Seaborn, psycopg2)
Data source	Microsoft Excel
Environment	Jupyter Notebook / VS Code
📁 Project Structure
Banking-Analytics-Dashboard/
│
├── data/
│   └── Banking_Data.xlsx
├── notebooks/
│   └── bank_EDA.ipynb
├── powerbi/
│   ├── Banking_Dashboard.pbix
│   └── Bankin_Analytics.pbix
├── images/
│   ├── HOME.png
│   ├── LOAN_ANALYSIS.png
│   ├── DEPOSIT_ANALYSIS.png
│   ├── SUMMARY.png
│   └── Drill_Through.png
├── docs/
│   └── Banking_Report.docx
└── README.md
🚀 How to Run
Clone the repository
bash
   git clone https://github.com/yourusername/Banking-Analytics-Dashboard.git
   cd Banking-Analytics-Dashboard
Open the dashboard: open a .pbix file from the powerbi/ folder in Power BI Desktop.
Run the EDA notebook (optional):
bash
   pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary
   jupyter notebook notebooks/bank_EDA.ipynb

Load data/Banking_Data.xlsx into a PostgreSQL database named banking_analytics (table customer_data), and update the connection details in the notebook with your own credentials.

👨‍💻 Author

Ravi Nandan Senior Market Research Analyst | Data Analytics Enthusiast

📧 Email: ravinandanyadavwork@gmail.com 💼 LinkedIn: https://www.linkedin.com/in/ravi-nandan-yadav-156a6a15a/ 💻 GitHub: https://github.com/yourusername
