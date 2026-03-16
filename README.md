# Olist E-Commerce Analysis

### Author: Emmanuel Aregbesola
### Date: March 2026

---

## Overview

An end-to-end data analysis project on the Brazilian Olist e-commerce dataset.
The project covers data cleaning, exploratory analysis, and state-level business 
insights across 99,000+ customer records spanning 9 relational tables.

This is an early-career project. It has been reviewed, critiqued, and is actively 
being improved.

---

## Project Structure

### Notebook 1 — Data Cleaning
Cleans all 9 raw datasets covering customers, orders, products, sellers, payments, 
reviews, and geolocation. Handles missing values, duplicate rows, datetime 
conversions, and column corrections.

### Notebook 2 — Analysis and Visualization
Answers 14 business questions across 5 segments — customers, orders, products, 
sellers, and delivery — using SQL queries against a PostgreSQL database and Python 
visualizations.

---

## Key Business Questions Answered

- Which Brazilian states have the highest customer base and revenue?
- Which states have the highest average customer spend?
- Do high-priced products sell in lower quantities?
- Which months historically generate the highest revenue per state?
- Which states have the fastest and slowest delivery times?
- How accurate are estimated delivery dates vs actual delivery dates?
- Who are the top sellers by volume and average review score?

---

## Tools and Technologies

| Tool | Purpose |
|------|---------|
| Python | Core analysis language |
| pandas | Data manipulation and cleaning |
| matplotlib / seaborn | Data visualization |
| SQLAlchemy | Database connection |
| PostgreSQL | Querying via CTEs and window functions |
| Jupyter Notebook | Development environment |

---

## Dataset

Original data sourced from the 
[Olist dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

Nine tables used:

- `olist_customers_dataset.csv`
- `olist_geolocation_dataset.csv`
- `olist_order_items_dataset.csv`
- `olist_order_payments_dataset.csv`
- `olist_order_reviews_dataset.csv`
- `olist_orders_dataset.csv`
- `olist_products_dataset.csv`
- `olist_sellers_dataset.csv`
- `product_category_name_translation.csv`

---

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/FrequentNotebook/olist-ecommerce-analysis
```

### 2. Install dependencies
```bash
pip install pandas sqlalchemy matplotlib seaborn psycopg2 python-dotenv
```

### 3. Configure your database connection

In `Notebook 2`, locate the database connection cell and replace 
`<username>` and `<password>` with your local PostgreSQL credentials:
```python
engine = create_engine(
    "postgresql://<username>:<password>@localhost:5432/olist_database"
)
```

> **Recommended:** Use a `.env` file with `python-dotenv` to manage 
> credentials securely instead of hardcoding them.

### 4. Run the notebooks in order

- **Notebook 1 first** — generates the 9 cleaned CSV files
- **Notebook 2 second** — requires a running PostgreSQL instance 
  with the cleaned data loaded and the `customer_master` view created

---

## Known Limitations and What I Would Do Differently

This section exists because honest documentation is part of good data practice.

- Did not run `.describe()` on numeric columns during cleaning — 
  value validation was absent
- Dropped geolocation duplicates without aggregating coordinates 
  per zip code first
- No standalone EDA notebook — distributions, outliers, and 
  correlations were not explored before analysis
- Referential integrity across all 9 tables was never verified
- No `errors='coerce'` validation after datetime conversions — 
  silent NaT values were never checked

---

## Project Status

🔄 **Active** — full overhaul in progress based on technical review feedback.

Planned improvements:
- [ ] Full EDA notebook from scratch
- [ ] `.env` implementation for credential management
- [ ] Referential integrity checks across all tables
- [ ] Statistical value validation on all numeric columns
- [ ] Proper geolocation aggregation per zip code
- [ ] Consistent visualization styling throughout

---

## Connect

Open to feedback, corrections, and connections.

[LinkedIn](https://www.linkedin.com/in/emmanuel-aregbesola/)
