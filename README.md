# Brazilian E-Commerce Analysis (Olist Dataset)

## Project Overview
This project presents an end-to-end **exploratory and diagnostic data analysis** of the
Brazilian E-Commerce Public Dataset by Olist.  
The objective is to understand **delivery performance, customer satisfaction, and product
sales patterns**, and to translate these findings into actionable business insights.

The analysis focuses on *what happened* and *why*, rather than prediction, making it a
complete and well-scoped **data analytics case study**.

---

## Dataset
The dataset is provided by Olist and represents real e-commerce orders placed in Brazil.
It consists of multiple relational tables covering orders, items, payments, reviews,
products, sellers, customers, and geolocation data.

Source:  
https://www.kaggle.com/olistbr/brazilian-ecommerce

---

## Tools & Technologies
- Python  
- Pandas & NumPy  
- Matplotlib & Seaborn  
- Plotly (interactive visualizations)  
- Jupyter Notebook  

---

## Analytical Approach

The project follows a structured analytical workflow:

1. **Data Understanding & Cleaning**
   - Validation of data quality and logical constraints
   - Handling duplicates and missing values
   - Ensuring correct data types

2. **Data Integration & Order-Level Modeling**
   - Aggregation of item- and payment-level data to order level
   - Construction of a consistent, order-level analytical dataset

3. **Feature Engineering**
   - Delivery time and delay metrics
   - Late delivery indicators

4. **Exploratory Data Analysis (EDA)**
   - Delivery performance analysis
   - Customer satisfaction analysis
   - Product and sales performance analysis
   - Regional comparisons using visualizations

5. **Visualization & Interpretation**
   - Bar charts, heatmaps, and interactive geographic maps
   - Focus on interpretability and business relevance

---

## Key Findings

### Logistics & Delivery Performance
- Most orders are delivered on time, but late deliveries vary significantly by region.
- Higher late delivery rates are concentrated in parts of the North and Northeast,
  while the South and Southeast show more reliable performance.
- Late deliveries have
