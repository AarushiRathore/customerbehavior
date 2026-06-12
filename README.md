Customer Shopping Behavior Analysis
An end-to-end data engineering and analytics project focusing on consumer transactional behavior. This project leverages a robust modern data stack—utilizing Python (Pandas) for data ingestion, cleaning, and feature engineering, PostgreSQL for scalable relational data storage and structured business queries, and Power BI for dynamic, executive-level visual reporting.

The ultimate objective of this analysis is to parse transactional patterns across 3,900 consumer profiles, uncovering high-impact insights into spending behavior, demographic segmentation, product affinity, and subscription lifecycle dynamics to drive data-backed strategic decisions.

📋 Table of Contents
Project Overview

Dataset Architecture & Summary

Data Pipeline & Engineering (Python)

Structured Business Intelligence Queries (SQL)

Interactive Executive Dashboard (Power BI)

Strategic Business Recommendations

Tech Stack & Tools

🚀 Project Overview
In modern e-commerce and retail environments, interpreting granular transactional data is essential for maintaining a competitive edge. This repository demonstrates a systematic approach to identifying underlying spending behaviors, defining accurate consumer segments, analyzing product feature correlations, and optimizing subscription models.

By mapping out the entire data lifecycle—from messy raw fields to polished diagnostic dashboards—this project provides actionable intelligence designed to minimize customer churn, optimize promotional yields, and maximize customer lifetime value (CLV).

📊 Dataset Architecture & Summary
The analytical engine is built upon a dataset capturing detailed transaction records.

Dataset Dimensions: 3,900 distinct records across 18 specialized feature columns.

Core Architectural Attributes:

Demographic Vectors: Age, Gender, Location, Subscription Status

Transactional Granularity: Item Purchased, Category, Purchase Amount, Season, Size, Color

Behavioral Metrics: Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type

Data Quality Constraints: Identified and structurally handled 37 missing values within the Review Rating attribute.

🐍 Data Pipeline & Engineering (Python)
The initial stage of the data pipeline establishes data integrity and creates rich analytical features through programmatic engineering:

Data Ingestion & Structural Exploration: * Leveraged pandas for processing the raw transactional data.

Executed comprehensive diagnostic profiles using df.info() and descriptive distribution wrappers (df.describe()).

Imputation & Quality Engineering: * Addressed missingness in the Review Rating column by applying a localized median imputation stratified across corresponding product categories to maintain rating variances without introducing macro-level bias.

Schema Standardization: * Normalized disparate database column architectures into standardized snake_case naming conventions for streamlined SQL schema mapping and improved cross-platform code maintenance.

Advanced Feature Engineering:

age_group: Segmented continuous demographic fields into strategic categorical age cohorts.

purchase_frequency_days: Transformed qualitative temporal frequencies into discrete numeric tracking metrics.

Data Redundancy Elimination:

Conducted consistency checks between overlapping fields; determined a structural correlation between discount_applied and promo_code_used, programmatically deprecating the redundant promo code attribute.

Enterprise Storage Loading:

Connected the Python script to a PostgreSQL database instance and loaded the fully cleaned DataFrame into database tables for relational SQL queries.

💻 Structured Business Intelligence Queries (SQL)
With the clean transactional schema residing in PostgreSQL, deep quantitative querying was conducted to evaluate core business pillars. Key investigative findings include:

1. Revenue Disaggregation by Gender
Analyzed the total revenue contribution across gender vectors to evaluate overarching purchasing power.

Male: $157,890

Female: $75,191

2. High-Yield Discount Users
Identified an elite behavioral customer sub-segment consisting of 839 specific profiles who successfully leveraged promotional discounts yet maintained individual transaction values significantly higher than the global average purchase amount.

3. Core Product Satisfaction Performance
Ranked top-performing consumer offerings based on absolute average customer satisfaction reviews:

Gloves: 3.86 rating

Sandals: 3.84 rating

Boots: 3.82 rating

Hat: 3.80 rating

Skirt: 3.78 rating

4. Shipping Logistics & Order Value Correlation
Evaluated whether shipping speeds affected premium basket sizes. The variance indicates premium fulfillment methods correlate with marginally higher order values:

Express Shipping Average Spend: $60.48

Standard Shipping Average Spend: $58.46

5. Subscription Contribution Metrics
Quantified transactional discrepancies across subscription states to discover whether contractual programs drove enhanced individual transactions.

Subscribers (Yes): 1,053 customers | $59.49 Avg Spend | $62,645.00 Total Revenue

Non-Subscribers (No): 2,847 customers | $59.87 Avg Spend | $170,436.00 Total Revenue

Insight: While individual transactional spend remains flat across both groups (~$59), non-subscribers drive the lion's share of absolute volume, signaling an aggressive acquisition opportunity for subscription conversion.

6. Discount-Dependent Elasticity Rankings
Identified the top 5 product lines displaying the highest ratio of promotional markdowns:

Hat: 50.00% discount rate

Sneakers: 49.66% discount rate

Coat: 49.07% discount rate

Sweater: 48.17% discount rate

Pants: 47.37% discount rate

7. Macro Customer Behavioral Segmentation
Classified the user base into distinct categorical buckets according to historic transactional volumes to target re-engagement plays:

Loyal Customers: 3,116 profiles

Returning Customers: 701 profiles

New Customers: 83 profiles

8. Category-Specific Dominance Matrix
Extracted top-performing products grouped within their broader retail categories:

Accessories: Jewelry (171 orders), Sunglasses (161 orders), Belt (161 orders)

Clothing: Blouse (171 orders), Pants (171 orders), Shirt (169 orders)

Footwear: Sandals (160 orders), Shoes (150 orders), Sneakers (145 orders)

Outerwear: Jacket (163 orders), Coat (161 orders)

9. Demographic Revenue Contribution
Tracked total cash generation across the engineered age groups:

Young Adult: $62,143

Middle-aged: $59,197

Adult: $55,978

Senior: $55,763

📊 Interactive Executive Dashboard (Power BI)
To synthesize these complex relational tables, a dynamic BI visualization dashboard was created to act as a singular source of retail truth.

Key Visual Interfaces & Analytical Controls:
High-Level KPI Cards: Surface mission-critical global values immediately—featuring total unique customer scale (3.9K), exact global average purchase amount ($59.76), and macro-satisfaction baseline (3.75 out of 5.0).

Cross-Filtering Slice Panels: Allows stakeholders to instantly drill down into multi-dimensional views based on Subscription Status, Gender, Product Category, and Shipping Type.

Subscription Composition Breakdown: A clear visual donut chart mapping the 73% Non-Subscriber vs. 27% Subscriber distribution split
