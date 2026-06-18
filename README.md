# D2C Customer Churn Intelligence - Part 2

## RFM Segmentation and Retention Strategy

---

# Project Overview

This project is designed to uncover customer retention opportunities for a Direct-to-Consumer (D2C) personal care company before introducing any machine learning solutions.

The primary goal is to analyze purchasing patterns, group customers into actionable business segments, and propose targeted retention initiatives that improve customer lifetime value while increasing marketing efficiency.

The segmentation framework combines conventional RFM methodology with supplementary behavioral indicators to deliver a more comprehensive view of customer health and engagement.

---

# Business Problem

Applying a single retention strategy across the entire customer base often leads to unnecessary marketing costs and lower campaign performance.

This project addresses that issue by categorizing customers based on:

* Purchase recency.
* Purchase frequency.
* Customer spending value.
* Product return behavior.
* Customer support complaints.
* Website engagement activity.
* Discount dependency.

The resulting customer segments help CRM teams focus their retention efforts where they can generate the greatest business impact.

---

# Dataset Used

The analysis incorporates multiple datasets from the D2C customer data package:

* customers.csv
  Stores customer demographic and profile-related information.

* orders.csv
  Stores historical transaction data used to calculate RFM metrics.

* support_tickets.csv
  Stores customer complaints and support service records.

* web_events_snapshot.csv
  Stores recent website and application engagement activity.

* intervention_history.csv
  Stores historical retention and campaign interaction data.

---

# Data Leakage Prevention

Customer segmentation is built using only information available up to the snapshot date.

Snapshot Date: 2025-09-30

Any orders occurring after the snapshot date are excluded before feature creation to maintain realistic and leakage-free business analysis.

---

# RFM Feature Engineering

Three fundamental RFM metrics are generated for each customer:

## Recency

Represents the number of days since the customer's latest purchase.

A lower recency value suggests stronger recent engagement.

---

## Frequency

Represents the total count of historical purchases made by a customer.

A higher frequency value indicates stronger loyalty and repeat purchasing behavior.

---

## Monetary Value

Represents the total revenue contribution after accounting for transaction-level discounts.

Higher monetary values identify customers with greater business value.

---

# Additional Behavioral Features

To strengthen customer profiling, several non-RFM behavioral signals are incorporated:

## Return Rate

Represents the proportion of customer orders that resulted in returns.

Higher return rates may signal dissatisfaction or product-related concerns.

## Support Complaint Count

Represents the total number of customer support interactions.

A larger number of complaints may indicate a poor customer experience.

## Website Engagement

Represents customer activity through sessions, product views, and campaign interactions.

Higher engagement levels suggest ongoing customer interest.

## Discount Dependency

Represents the average level of discount usage across customer purchases.

High dependency may indicate strong sensitivity to promotional pricing.

---

# Customer Segments Created

Exactly five customer segments are generated:

## 1. Champions

Highly valuable customers characterized by recent purchases, frequent transactions, and strong experience-related indicators.

---

## 2. Loyal Customers

Customers who consistently engage with the brand through stable purchasing behavior and long-term loyalty.

---

## 3. High Value but Unhappy Customers

Revenue-generating customers who exhibit dissatisfaction through complaints, returns, or other negative experience signals.

---

## 4. Discount Sensitive Customers

Customers who purchase regularly but rely heavily on discounts and promotional incentives.

---

## 5. Dormant and At Risk Customers

Customers displaying low engagement levels, infrequent recent activity, or signs of weakening brand relationships.

---

# Repository Structure

The repository contains the following files:

```text
D2C-RFM-Retention-Strategy/
│
├── rfm_segmentation.ipynb        # Complete segmentation notebook
├── segments.csv                  # Final customer segmentation output
├── retention_strategy.md         # Segment retention recommendations
├── manual_review_cases.md        # Complex customer review cases
├── README.md                     # Project documentation
└── requirements.txt              # Python dependencies
```
