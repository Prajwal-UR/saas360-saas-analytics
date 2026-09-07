# saas360-saas-analytics
End-to-end SaaS analytics project using Python, SQL, Excel and Power BI to analyze customer retention, churn, product engagement and revenue.

# SaaS360 — SaaS Product Growth, Retention & Revenue Intelligence

An end-to-end SaaS analytics and Business Intelligence project built to analyze customer growth, subscription performance, product engagement, churn, retention, and revenue.

SaaS360 demonstrates how raw SaaS data can be transformed into business insights using Python, SQL, Excel, and Power BI.

---

## Project Overview

SaaS companies need to continuously understand:

- Who their customers are
- Which subscription plans generate the most revenue
- How customers engage with the product
- Where churn is occurring
- What factors are associated with churn
- Which customers contribute the most revenue
- Where retention efforts should be focused

SaaS360 addresses these questions through an end-to-end analytics workflow:

**Raw Data → Data Quality → Python Cleaning & EDA → SQL Analysis → KPI Validation → Power BI Modeling & DAX → Interactive Dashboard → Business Insights**

---

## Business Objective

The objective of SaaS360 is to build a decision-support analytics solution for a SaaS business by connecting:

**Customer → Subscription → Product Usage → Support → Churn → Revenue**

The project focuses on four major business areas:

1. Customer analysis
2. Product engagement
3. Churn and retention
4. Revenue intelligence

---

## Dataset

The project uses the **SaaS Subscription & Churn Analytics Dataset** representing a fictional SaaS company, RavenStack.

The dataset is synthetic and contains five related business tables:

| Dataset | Records | Purpose |
|---|---:|---|
| Accounts | 500 | Customer profiles and churn information |
| Subscriptions | 5,000 | Plans, seats, MRR, ARR, upgrades, downgrades and billing |
| Feature Usage | 25,000 | Product feature usage and errors |
| Support Tickets | 2,000 | Customer support activity and satisfaction |
| Churn Events | 600 | Churn dates, reasons, refunds and feedback |

Dataset source:

https://www.kaggle.com/datasets/rivalytics/saas-subscription-and-churn-analytics-dataset

The dataset is synthetic and is used for educational and analytical purposes.

---

## Technology Stack

### Python

Used for data preparation and exploratory analysis.

- Data loading
- Data quality assessment
- Missing-value analysis
- Duplicate detection
- Data cleaning and transformation
- Exploratory Data Analysis (EDA)

### SQL / MySQL

Used for relational analysis and business KPI calculations.

- Multi-table joins
- Aggregations
- Customer revenue analysis
- Churn analysis
- Revenue by plan
- Industry-level analysis
- Common Table Expressions (CTEs)
- Window functions
- Customer revenue ranking

### Excel

Used for KPI validation and reconciliation.

- KPI validation
- Data reconciliation
- Analytical verification

### Power BI

Used for data modeling, DAX and interactive business intelligence reporting.

- Data modeling
- Relationships
- DAX measures
- Interactive slicers
- KPI cards
- Key Influencers
- Scatter analysis
- Matrix analysis
- Ribbon chart
- Business-focused dashboard design

---

## Data Model

The Power BI model follows a relational structure centered around customer accounts and subscriptions.

```text
                    ┌────────────────────┐
                    │   accounts_clean   │
                    │   Customer Data     │
                    └─────────┬──────────┘
                              │
             ┌────────────────┼─────────────────┐
             │                │                 │
             ▼                ▼                 ▼
   ┌─────────────────┐ ┌───────────────┐ ┌─────────────────┐
   │ subscriptions   │ │   support     │ │     churn       │
   │     _clean      │ │  tickets      │ │    events       │
   └────────┬────────┘ └───────────────┘ └─────────────────┘
            │
            ▼
   ┌─────────────────┐
   │ feature_usage   │
   │     _clean      │
   └─────────────────┘
