🏦 Loan Eligibility Automation System (MySQL)

A MySQL-based project that automatically evaluates loan applications using a stored procedure and a trigger. When a new application is inserted, its status is set to Approved or Rejected based on predefined eligibility rules, with no manual review step.

Note: Built as a learning project using sample data to practice database automation concepts.

📌 Features
Relational schema with primary and foreign key constraints
Eligibility rules encapsulated in a reusable stored procedure
Trigger that applies the rules automatically on every new loan record
Python integration (MySQL Connector + Pandas) for inserting data and analyzing results
Jupyter Notebook for query execution and result summary
🧠 Eligibility Rules

An application is Approved only if all three conditions are met:

Criterion	Condition
Age	≥ 21
Credit Score	≥ 700
Income	≥ 40% of the requested loan amount

Otherwise, it is Rejected.

sql
CASE
    WHEN Age >= 21
     AND CreditScore >= 700
     AND Income >= (LoanAmount * 0.4)
    THEN 'Approved'
    ELSE 'Rejected'
END
🔄 How It Works
New loan record inserted
          │
          ▼
   Trigger fires automatically
          │
          ▼
 Eligibility logic is applied
 (stored procedure / rule set)
          │
          ▼
 Status stored as Approved / Rejected
🛠️ Tech Stack
Area	Tools
Database	MySQL (stored procedures, triggers, joins, foreign keys)
Language	Python (Pandas, MySQL Connector)
Environment	Jupyter Notebook
📁 Project Structure
loan-eligibility-system/
├── schema.sql                    # Database tables and relationships
├── eligibility-check.sql         # Stored procedure and trigger
├── loan-eligibility-check.ipynb  # Python notebook: insert data, run queries
└── README.md
📊 Results (Sample Data)

Tested on 40 sample applications:

Status	Count	Percentage
Approved	31	77.5%
Rejected	9	22.5%
Total	40	100%

These figures reflect the sample dataset and the rules above; they are not real lending data.

🚀 Getting Started
Prerequisites
MySQL Server 8.0+
Python 3.8+
Jupyter Notebook
Python packages: pandas, mysql-connector-python
bash
pip install pandas mysql-connector-python notebook
Setup
Create the database
sql
CREATE DATABASE loan_system;
USE loan_system;
Create the tables
bash
mysql -u <user> -p loan_system < schema.sql
Create the procedure and trigger
bash
mysql -u <user> -p loan_system < eligibility-check.sql
Insert data
Manually with SQL INSERT statements, or
Through loan-eligibility-check.ipynb (update the connection details in the first cell).
Verify
sql
SELECT Status, COUNT(*) AS total
FROM <your_loan_table>
GROUP BY Status;

Replace <your_loan_table> with the loan table name defined in schema.sql.

⚠️ Limitations
Uses sample data and a single, simple rule set
No handling of NULL or invalid inputs (e.g., negative income)
No rejection reason or audit log is stored
🔮 Future Improvements
Store a rejection reason (low credit score, insufficient income, underage)
Add an audit log table for every decision
Add input validation and CHECK constraints
Test with a larger, generated dataset
Add analysis by age group, income bracket, and credit score band
Introduce risk tiers and EMI calculation
