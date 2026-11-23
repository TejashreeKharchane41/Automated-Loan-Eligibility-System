
# 🏦 SQL Automated Loan Eligibility System

## 🚀 Project Overview

This project is a fully automated backend loan approval system powered by **SQL Stored Procedures** and **Triggers**. It evaluates loan applications in real-time based on key financial metrics—age, income, credit score, and requested loan amount—and instantly updates the application status upon data insertion.

Built using **MySQL**, **Python**, and **Jupyter Notebook**, the system ensures seamless decision-making with zero manual intervention.

---

## 🧠 Eligibility Criteria Logic

Loan applications are evaluated automatically using the following SQL rule:

```sql
CASE 
    WHEN Age >= 21 
     AND CreditScore >= 700 
     AND Income >= (LoanAmount * 0.4)
    THEN 'Approved'
    ELSE 'Rejected'
END

```

---

## 🔧 Technologies Used

* **MySQL:** Stored Procedures, Triggers, Relational Schema, Joins, Foreign Keys
* **Python:** Pandas, MySQL Connector
* **Jupyter Notebook:** Query Execution, Data Visualization

---

## ⚙️ Automation Features

* ✅ **Stored Procedure:** Encapsulates the core eligibility evaluation logic.
* 🔁 **Trigger:** Automatically invokes the stored procedure whenever new loan data is inserted.
* 📊 **Live Status Update:** Loan status is instantly marked as `Approved` or `Rejected` in the database.

---

## 📈 Outcome Summary

Out of **40** processed loan applications:

| Application Status | Count | Percentage |
| --- | --- | --- |
| **Approved** | 31 | 77.5% |
| **Rejected** | 9 | 22.5% |
| **Total** | **40** | **100%** |

> **Note:** All new incoming applications are evaluated instantaneously upon database insertion.

---

## 🏁 How to Run This Project

1. **Create the Database:** Set up a new MySQL database named `loan_system`.
2. **Build the Schema:** Execute `schema.sql` to create the required relational tables.
3. **Configure Automation:** Run `eligibility-check.sql` to initialize the eligibility logic, stored procedures, and triggers.
4. **Insert Data:** Add new applicant records manually via SQL or programmatically through `loan-eligibility-check.ipynb`.
5. **Visualize Results:** Launch `notebooks/loan_eligibility_check.ipynb` to query the database and view visual analytics.

```

```
