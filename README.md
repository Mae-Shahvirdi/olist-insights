# Brazilian E-Commerce Analysis (Olist Dataset)

## 📌 Project Overview
This project explores and prepares the **Brazilian E-Commerce Public Dataset by Olist** for analysis.  
The goal of this phase is **data cleaning, validation, and integration readiness**, ensuring that all tables are reliable, logically consistent, and safe to join before any analysis or modeling.

The dataset represents real e-commerce transactions made at Olist, a Brazilian marketplace that connects small businesses to customers.

---

## 📂 Dataset Description
The Olist dataset is a **relational dataset** composed of multiple tables representing different aspects of the e-commerce lifecycle.

### Tables used in this project:
- **orders** – central table describing the order lifecycle  
- **order_items** – individual items within each order  
- **order_payments** – payment transactions per order  
- **order_reviews** – customer reviews and ratings  
- **products** – product metadata and physical attributes  
- **sellers** – seller location and identification  
- **customers** – customer location data  
- **product_category_translation** – Portuguese → English category mapping  
- **geolocation** – latitude/longitude reference data  

---

## 🧹 Data Cleaning & Validation Strategy

A reusable helper function (`clean_basics`) was used across tables to:
- remove duplicate rows
- convert date columns to proper `datetime` format

All other cleaning steps were **table-specific** and focused on:
- validating business keys (table grain)
- enforcing logical constraints
- preserving meaningful missing values

No imputation or arbitrary data removal was performed.

---

## ✅ Cleaning Summary by Table

### 1. Orders (`orders`)
- One row per `order_id`
- Converted all lifecycle timestamps to datetime
- Validated primary key uniqueness
- Checked logical date ordering (delivery cannot occur before purchase)
- Preserved missing lifecycle dates as meaningful (e.g. canceled orders)

---

### 2. Order Items (`order_items`)
- One row per (`order_id`, `order_item_id`)
- Converted shipping deadline to datetime
- Validated non-negative prices and freight values
- Confirmed business-key uniqueness
- Ready for joins without risk of row multiplication

---

### 3. Order Payments (`order_payments`)
- One row per (`order_id`, `payment_sequential`)
- Removed duplicate safety rows
- Validated payment-sequence uniqueness
- Preserved multiple payments per order (installments, mixed methods)

---

### 4. Order Reviews (`order_reviews`)
- Reviews are optional; missing text was preserved
- Converted review timestamps to datetime
- Validated review score range (1–5)
- Resolved multiple reviews per order by keeping the **latest review**
- Final grain: one review per order

---

### 5. Products (`products`)
- One row per `product_id`
- Validated uniqueness of product identifiers
- Checked physical attributes for non-negative values
- Preserved missing metadata as incomplete seller information

---

### 6. Sellers (`sellers`)
- One row per `seller_id`
- Validated uniqueness and state code format
- No missing values or inconsistencies found

---

### 7. Product Category Translation (`product_category_translation`)
- One row per product category
- Verified unique category-to-translation mapping
- Used as a lookup table for enrichment

---

### 8. Geolocation (`geolocation`)
- Validated latitude and longitude bounds for Brazil
- Removed invalid coordinate entries
- Prepared for optional spatial analysis

---

## 🛠 Tools & Technologies
- **Python**
- **Pandas**
- **Jupyter Notebook**
- **Kaggle API**

---

## 📈 Current Project Status
✔ All tables cleaned and validated  
✔ Business keys and grains confirmed  
✔ Dataset is **integration-ready**

---

## 🔜 Next Steps
- Integrate tables into a master analytical dataset
- Perform exploratory data analysis (EDA)
- Analyze delivery performance, customer satisfaction, and revenue drivers
- Build dashboards (Power BI / Tableau) or predictive models

---

## 📎 Data Source
Brazilian E-Commerce Public Dataset by Olist  
Available on Kaggle: https://www.kaggle.com/olistbr/brazilian-ecommerce

---

## ✍️ Author
Mae Shahvirdi  

Data Analytics | Python | SQL | BI | UX Background
