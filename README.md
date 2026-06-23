# 🏦 Bank Financial Analytics Dashboard | Power BI

## 📌 Project Overview

The **Bank Financial Analytics Dashboard** is an end-to-end Power BI solution designed to analyze banking transactions, customer behavior, operational performance, and financial KPIs. The dashboard provides management-level insights through interactive visualizations, dynamic metrics, and year-over-year performance comparisons.

This project demonstrates advanced Power BI concepts including:

- Data Modeling (Star Schema)
- DAX Measures & Time Intelligence
- Dynamic Metric Switching (Field Parameters)
- KPI Dashboard Design
- Interactive Slicers & Filters
- Custom Navigation Panel
- Customer Segmentation Analysis
- Financial Transaction Analytics

---

## 📊 Dashboard Preview

### Overview Analysis Page

> Add screenshot here

![Overview Dashboard](images/overview_dashboard.png)

### Transactions Analysis Page

> Add screenshot here

![Transactions Dashboard](images/transactions_dashboard.png)

---

# 🎯 Business Problem

Banks generate thousands of transactions daily across multiple channels and customer segments.

Management requires a centralized dashboard to:

- Monitor transaction performance
- Track revenue and fees
- Analyze customer segments
- Evaluate geographic performance
- Compare current performance against previous year
- Identify operational trends and patterns

This dashboard addresses these requirements through an interactive reporting solution.

---

# 📂 Dataset Information

The solution uses four tables:

## 1. finance_transactions (Fact Table)

Contains transactional information such as:

- Transaction ID
- Transaction Date
- Customer ID
- Transaction Amount
- Fee Amount
- Tax Amount
- Transaction Type
- Transaction Status
- Merchant Category
- Channel
- Fraud Flag
- Risk Score

---

## 2. customers (Dimension Table)

Contains customer demographic information:

- Customer ID
- Customer Name
- Gender
- Occupation
- City
- State
- Customer Segment
- Annual Income
- Join Date
- Date of Birth

---

## 3. Calendar Table (Date Dimension)

Used for Time Intelligence calculations.

Fields:

- Date
- Month
- Month Number
- Year

---

## 4. Dynamic Metric Table

Field Parameter Table used for dynamic metric switching.

Fields:

- Dynamic Metric
- Dynamic Metric Fields
- Dynamic Metric Order
- Dynamic Title

---

# 🏗 Data Model

The project follows a **Star Schema** architecture.

```text
                Customers
                    |
                    |
                    |
Finance Transactions -------- Calendar Table

       Dynamic Metric
      (Disconnected)
```

### Relationships

| From | To | Cardinality |
|--------|------|------------|
| customers[customer_id] | finance_transactions[customer_id] | One-to-Many |
| Calendar Table[Date] | finance_transactions[transaction_date] | One-to-Many |
| Dynamic Metric | Disconnected | Parameter Table |

---

# 📈 Key KPIs

The dashboard tracks:

### Total Amount
Total transaction value processed.

### Total Transactions
Total count of banking transactions.

### Average Transaction Value
Average transaction amount.

### Total Fee Amount
Total fees collected by the bank.

### Total Tax
Total tax generated from transactions.

---

# 📊 DAX Measures Used

## Core Measures

```DAX
Total Amount =
SUM(finance_transactions[amount])
```

```DAX
Total Transactions =
COUNT(finance_transactions[transaction_id])
```

```DAX
Avg Transaction Value =
DIVIDE([Total Amount],[Total Transactions])
```

```DAX
Total Fee Amount =
SUM(finance_transactions[fee_amount])
```

```DAX
Total Tax =
SUM(finance_transactions[tax_amount])
```

---

## Time Intelligence Measures

### Previous Year Measures

- PY Amount
- PY Fee Amount
- PY Tax Amount
- PY Transaction
- PY Avg Transaction

### YOY Measures

- YOY Amount
- YOY Fee Amount
- YOY Tax Amount
- YOY Transaction
- YOY Avg Transaction

### YOY % Measures

- YOY %
- YOY % Amount
- YOY % Fee Amount
- YOY % Tax Amount
- YOY % Avg Transaction

---

# 🔄 Dynamic Metric Feature

A Dynamic Metric slicer allows users to switch dashboard visuals between:

- Total Amount
- Total Transactions
- Average Transaction Value
- Fee Amount
- Tax Amount

This functionality is implemented using **Power BI Field Parameters**.

Benefits:

- Reduces dashboard clutter
- Enhances interactivity
- Improves user experience

---

# 📊 Dashboard Pages

## Page 1: Overview Analysis

### KPIs

- Total Amount
- Total Transactions
- Avg Transaction Value
- Total Fee Amount
- Total Tax

### Visuals

#### Total Amount by Month
Trend analysis showing monthly transaction performance.

#### Transaction Status Analysis
Distribution of:

- Success
- Failed
- Pending

#### Customer Segment Analysis

Segments:

- Retail
- Premium
- SME
- Corporate
- Wealth

#### State Analysis

Performance by state:

- Karnataka
- West Bengal
- Uttar Pradesh
- Maharashtra
- Haryana
- Gujarat
- Chandigarh

#### Transaction Type Analysis

Categories:

- Withdrawal
- Transfer
- Refund
- Loan EMI
- Investment
- Interest Credit
- Fee Charge
- Deposit
- Card Payment
- Bill Payment

#### Gender Analysis

Comparison of transaction contribution by:

- Male
- Female

---

## Page 2: Transactions

Provides detailed row-level transaction analysis including:

- Transaction ID
- Customer Name
- Transaction Type
- Transaction Status
- State
- Customer Segment
- Amount
- Fee Amount
- Tax Amount

---

# 🎨 Dashboard Features

## Navigation Panel

Custom navigation buttons:

- Overview Analysis
- Transactions

Provides a professional application-style user experience.

---

## Interactive Slicers

Users can filter by:

### Year

Example:

- 2024

### Dynamic Metric

Example:

- Total Amount
- Total Transactions

### Occupation

Example:

- Business Owner

### Category

Example:

- Education

---

# 📌 Business Insights

### Customer Segments

Retail and Premium customers contribute the largest transaction volume.

### Transaction Success Rate

Most transactions are successfully processed, indicating operational efficiency.

### Geographic Concentration

Transaction activity is concentrated in a limited number of high-performing states.

### Revenue Streams

Fee and tax metrics provide visibility into non-interest income sources.

---

# 🛠 Tools & Technologies

| Tool | Purpose |
|--------|----------|
| Power BI Desktop | Dashboard Development |
| DAX | Data Modeling & Calculations |
| Power Query | Data Transformation |
| Field Parameters | Dynamic Metric Switching |
| Star Schema | Data Modeling |

---

# 🚀 Future Enhancements

Potential future improvements:

- Fraud Detection Dashboard
- Customer Lifetime Value Analysis
- Predictive Forecasting
- Branch Performance Analytics
- AI-Powered Insights
- Drill-through Detail Pages
- Advanced Risk Analytics
Allowable file size was less than 100 Mb so here is link for the dashbaord
[Bank's Financial Data Analytics]-- (https://drive.google.com/file/d/1J1_8QtUclCWin9z0Ygu-s5Bl4FX6dFKh/view?usp=sharing)

---

# 👨‍💻 Author

**Kartik**

Aspiring Data Analyst | Power BI Developer | Business Intelligence Enthusiast

---

# ⭐ If you found this project useful, please consider starring the repository.
