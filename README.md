
# D2C Customer Churn Intelligence - Part 2
## RFM Segmentation and Retention Strategy

---

# Project Overview

This project focuses on identifying customer retention opportunities for a Direct-to-Consumer (D2C) personal care brand before deploying any machine learning model.

The objective is to understand customer purchasing behavior, classify customers into meaningful business segments, and recommend personalized retention actions that maximize customer lifetime value and marketing return on investment.

The segmentation approach combines traditional RFM analysis with additional behavioral signals to provide a complete understanding of customer health.

---

# Business Problem

Providing the same retention campaign to every customer creates unnecessary marketing expenses and reduces campaign effectiveness.

This project solves this challenge by identifying different customer groups based on:

- Purchase recency.
- Purchase frequency.
- Customer spending value.
- Product return behavior.
- Customer support complaints.
- Website engagement activity.
- Discount dependency.

The generated customer segments allow the CRM team to prioritize high-impact retention activities.

---

# Dataset Used

The analysis uses multiple datasets from the D2C customer data package:

- customers.csv  
  Contains customer demographic and profile information.

- orders.csv  
  Contains historical transaction records used for RFM calculations.

- support_tickets.csv  
  Contains customer complaints and service interactions.

- web_events_snapshot.csv  
  Contains recent website and application engagement behavior.

- intervention_history.csv  
  Contains previous retention campaign information.

---

# Data Leakage Prevention

The customer segmentation uses only information available until the snapshot date:

Snapshot Date: 2025-09-30

All orders after the snapshot date are removed before feature engineering to ensure realistic business decision making.

---

# RFM Feature Engineering

Three core RFM metrics are created for every customer:

## Recency

Measures the number of days since the customer's most recent purchase.

Lower recency indicates stronger current engagement.

---

## Frequency

Measures the total number of historical purchases.

Higher frequency indicates stronger customer loyalty.

---

## Monetary Value

Measures the total revenue contribution after applying transaction discounts.

Higher monetary value represents greater customer importance.

---

# Additional Behavioral Features

To improve customer understanding, the following non-RFM signals are included:

## Return Rate

Measures the percentage of customer orders that were returned.

Higher return rates may indicate dissatisfaction or product issues.

## Support Complaint Count

Measures the total number of customer support interactions.

More complaints may indicate a negative customer experience.

## Website Engagement

Measures customer activity using sessions, product views, and campaign interactions.

Higher engagement indicates continued customer interest.

## Discount Dependency

Measures average discount usage across purchases.

High dependency suggests customers are sensitive to promotional pricing.

---

# Customer Segments Created

Exactly five customer segments are created:

## 1. Champions

High-value customers with frequent recent purchases and excellent experience indicators.

---

## 2. Loyal Customers

Customers with consistent purchasing behavior and strong long-term engagement.

---

## 3. High Value but Unhappy Customers

Customers generating high revenue but showing dissatisfaction through complaints or returns.

---

## 4. Discount Sensitive Customers

Customers who purchase frequently but depend heavily on promotional offers.

---

## 5. Dormant and At Risk Customers

Customers with low engagement, old purchases, or declining relationships with the brand.

---

# Repository Structure

The repository contains the following files:
