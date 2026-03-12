# Bank_Domain_Data_Analyst_Project

# Banking Risk Analytics Dashboard

A Power BI dashboard solution for risk analytics in banking and financial services. This project helps financial institutions make data-driven lending decisions by analyzing client profiles, loan patterns, and deposit trends to minimize the risk of loan defaults.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)

---

## Overview

This dashboard analyzes banking data to identify patterns in client behavior, assess loan risk, and track deposit trends. By visualizing key metrics across different client segments (income bands, engagement timeframes, nationalities), banks can make informed decisions about loan approvals and client management.

---

## Features

- **Loan Analysis** - Track bank loans, business lending, and credit card balances
- **Deposit Analysis** - Monitor bank deposits, savings accounts, checking accounts, and foreign currency accounts
- **Client Segmentation** - Analyze clients by income band, engagement timeframe, and nationality
- **Risk Assessment** - Evaluate client profiles to predict loan repayment likelihood
- **Interactive Filters** - Filter by banking relationship, gender, investment advisor, and time periods

---

## Dataset Structure

The project uses five interconnected tables:

| Table | Description |
|-------|-------------|
| `Clients - Banking` | Core client data including demographics, accounts, and loans |
| `Banking Relationship` | Types of banking relationships (Private Bank, etc.) |
| `Gender` | Gender dimension table |
| `Investment Advisor` | Advisor assignment data |
| `Period` | Time dimension for temporal analysis |

---

## Key Metrics (KPIs)

| Metric | DAX Formula |
|--------|-------------|
| Total Clients | `DISTINCTCOUNT('Clients - Banking'[Client ID])` |
| Total Loan | `[Bank Loan] + [Business Lending] + [Credit Cards Balance]` |
| Total Deposit | `[Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]` |
| Total Fees | `SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])` |
| Bank Deposit | `SUM('Clients - Banking'[Bank Deposits])` |

---

# Dashboard Pages

- **Home** – Overview with key metrics and navigation
- **Loan Analysis** – Detailed loan metrics by client segments
- **Deposit Analysis** – Deposit trends across account types and demographics
- **Summary** – Consolidated view of all major KPIs
