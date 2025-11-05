# Olist E-Commerce Data Analysis — Ongoing Project
Olist E-Commerce Analytics — an ongoing project to clean, explore, and analyze the Brazilian Olist e-commerce dataset using Python and pandas, preparing it for insights on customer behavior, payments, and satisfaction.

# Overview
This project explores and cleans the Olist Brazilian E-Commerce dataset, a large real-world dataset containing customer, order, payment, product, and review information.
The goal is to prepare a clean, analysis-ready dataset to study key business questions such as:

- Customer behavior and satisfaction
- Payment methods and spending patterns
- Delivery performance and logistics
- Seller and product insights

The project is being developed iteratively — with each dataset cleaned, validated, and documented before merging.

## Datasets Processed So Far
The following tables from the Olist dataset have been explored and cleaned up to this point:

| Dataset            | Rows                | Columns | Main Focus                                   | Cleaning Status                                   |
| ------------------ | ------------------- | ------- | -------------------------------------------- | ------------------------------------------------- |
| **geolocation**    | 1,000,163 → 738,307 | 5       | Latitude/longitude, city/state, ZIP prefixes | ✅ Cleaned (duplicates + invalid coords removed)   |
| **customers**      | 99,441              | 5       | Customer IDs, ZIP prefixes, cities/states    | ✅ Cleaned earlier                                 |
| **order_items**    | 112,650             | 7       | Product-level details per order              | ✅ Cleaned (dates + numeric validation)            |
| **order_payments** | 103,886             | 5       | Payment methods and values                   | ✅ Cleaned (kept 9 valid zero-value payments)      |
| **order_reviews**  | 99,224              | 7       | Customer feedback and review scores          | ✅ Cleaned (dates converted, missing text handled) |


## Cleaning Highlights

## General Steps
Across all datasets, the following cleaning principles were applied:

- Checked and removed duplicate rows.
- Validated and standardized column data types.
- Converted string-based date columns to datetime.
- Verified numeric ranges and handled potential outliers.
- Removed invalid geolocations and redundant records.
- Kept rare but legitimate edge cases (e.g., 0-value payments).
- Preserved missing text fields rather than filling them artificially.

## Example: Review Dataset:
- review_comment_title: only ~12 % filled — optional field, most customers skipped it.
- review_comment_message: ~41 % filled — expected behavior.
- review_score: all valid (1–5), mean = 4.09, median = 5 → customers are generally satisfied.
- Dates converted for future analysis (e.g., review response time).

## Current Progress
Cleaned and validated the major supporting tables.
Preparing for data merging and feature engineering, combining customer, order, and review data to enable deeper insights

## Next Steps
- Clean remaining tables (orders, sellers, products).
- Merge all cleaned datasets into a master analytical table.
- Create KPIs for delivery time, payment trends, and satisfaction.
- Visualize findings in Python (Matplotlib / Seaborn / Plotly).
- Publish summary insights and Jupyter notebook.

## Tech Stack
- Language: Python (Pandas, NumPy)
- Environment: Jupyter Notebook
- Version control: Git + GitHub
- Visualization (planned): Matplotlib, Seaborn, Plotly
- Data source: Olist E-Commerce Dataset on Kaggle

