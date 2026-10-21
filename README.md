# Zepto Inventory SQL Data Analysis

SQL data analysis project on real e-commerce inventory data from **Zepto**, built with **PostgreSQL** and **pgAdmin**. It covers the full workflow: schema design, data exploration, data cleaning, and business-insight queries.

## Objectives
- Explore the dataset: row count, nulls, categories, stock status, duplicate product names
- Clean the data: remove zero-price records, convert prices from paise to rupees
- Answer business questions on pricing, discounts, stock, revenue, and inventory weight

## Tech Stack
- PostgreSQL
- pgAdmin 4
- SQL: aggregations, `CASE WHEN`, `GROUP BY`, `HAVING`, `ROUND`, `DISTINCT`

## Dataset
Zepto product inventory data (`zepto_v2.csv`, 3,732 rows) included in this repo.

| Column | Type | Description |
|---|---|---|
| sku_id | SERIAL (PK) | Unique product ID (auto-generated) |
| category | VARCHAR(120) | Product category |
| name | VARCHAR(150) | Product name |
| mrp | NUMERIC(8,2) | Maximum retail price |
| discountPercent | NUMERIC(5,2) | Discount percentage |
| availableQuantity | INTEGER | Units available |
| discountedSellingPrice | NUMERIC(8,2) | Price after discount |
| weightInGms | INTEGER | Product weight in grams |
| outOfStock | BOOLEAN | Stock status |
| quantity | INTEGER | Units per pack |

## Project Workflow
1. **Create table**: define schema with a primary key
2. **Data exploration**: row count, sample data, null check, distinct categories, in-stock vs out-of-stock, duplicate names
3. **Data cleaning**: delete rows with `mrp = 0`, convert paise to rupees
4. **Business analysis**: 8 queries (below)

## Business Questions Solved
| # | Question |
|---|---|
| Q1 | Top 10 best-value products by discount percentage |
| Q2 | High-MRP products (> ₹300) that are out of stock |
| Q3 | Estimated revenue per category |
| Q4 | Products with MRP > ₹500 and discount < 10% |
| Q5 | Top 5 categories by average discount |
| Q6 | Price per gram for products ≥ 100g, sorted by best value |
| Q7 | Group products into Low / Medium / Bulk by weight |
| Q8 | Total inventory weight per category |

## How to Run
1. Install PostgreSQL and pgAdmin
2. Create a database (e.g. `zepto_SQL_project`)
3. Run the table creation part of `Zepto_SQL_data_analysis_Project.sql`
4. Import `zepto_v2.csv` into the `zepto` table  
   (pgAdmin: right-click table > Import/Export Data, Header: ON, Encoding: UTF8, remove `sku_id` from columns)
5. Run the cleaning and analysis queries

## Repo Structure
```
├── README.md
├── Zepto_SQL_data_analysis_Project.sql
└── zepto_v2.csv
```

## Key Skills Demonstrated
- Database and table design
- Data cleaning in SQL
- Aggregate functions and grouping
- Conditional logic with `CASE`
- Turning raw data into business insights

## Credits
Built following [Amlan Mohanty's SQL portfolio project tutorial](https://www.youtube.com/watch?v=x8dfQkKTyP0) on YouTube.

## Author
**Dhurba** | Aspiring AI/ML & GenAI Engineer
