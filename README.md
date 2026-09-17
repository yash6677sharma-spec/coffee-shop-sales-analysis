# ☕ Coffee Shop Sales Analysis — SQL Project

A beginner-friendly SQL data analysis project based on coffee shop sales data. The project uses PostgreSQL to analyze sales, customers, products, cities, revenue, customer counts, product performance, monthly growth, rent, and estimated coffee-consumer populations.

## 📌 Project Overview

This project answers 10 business questions using SQL. It demonstrates practical SQL skills that are useful for a Data Analyst portfolio.

### Business Questions

1. **Coffee Consumers Count** — Estimate coffee consumers in each city using 25% of population.
2. **Total Revenue from Coffee Sales** — Calculate total revenue in Q4 2023 and revenue by city.
3. **Sales Count for Each Product** — Count orders/sales for every product.
4. **Average Sales Amount per City** — Calculate total revenue, unique customers, and average sale per customer by city.
5. **City Population and Coffee Consumers** — Compare estimated coffee consumers with unique customers.
6. **Top Selling Products by City** — Find the top 3 products in each city using `DENSE_RANK()`.
7. **Customer Segmentation by City** — Count unique customers purchasing the selected coffee products.
8. **Average Sale vs Rent** — Compare average sale per customer with estimated rent per customer.
9. **Monthly Sales Growth** — Calculate month-over-month sales growth by city using `LAG()`.
10. **Market Potential Analysis** — Combine revenue, rent, customers, estimated coffee consumers, and average sale per customer.

## 🗂️ Project Structure

```text
coffee-shop-sales-analysis/
│
├── data/
│   ├── city.csv
│   ├── customers.csv
│   ├── products.csv
│   └── sales.csv
│
├── sql/
│   ├── 01_create_tables.sql
│   └── 02_business_questions_answers.sql
│
└── README.md
```

## 🛠️ Tools & Technologies

- PostgreSQL
- pgAdmin
- SQL
- GitHub

## 🧠 SQL Concepts Used

- `SELECT`, `WHERE`, `GROUP BY`, `ORDER BY`
- Aggregate functions: `SUM()`, `COUNT()`, `COUNT(DISTINCT)`
- `JOIN`, `LEFT JOIN`
- `CASE`/filtering concepts
- Date functions: `EXTRACT()`
- Type casting with `::numeric`
- Common Table Expressions (`WITH` / CTEs)
- Window functions
- `LAG()`
- `DENSE_RANK()`
- Percentage growth calculations
- Revenue and customer analysis

## 🗃️ Database Schema

The database contains four related tables:

### `city`

| Column | Description |
|---|---|
| city_id | Primary key for city |
| city_name | City name |
| population | City population |
| estimated_rent | Estimated rent |
| city_rank | City rank |

### `customers`

| Column | Description |
|---|---|
| customer_id | Primary key for customer |
| customer_name | Customer name |
| city_id | Foreign key referencing `city` |

### `products`

| Column | Description |
|---|---|
| product_id | Primary key for product |
| product_name | Product name |
| price | Product price |

### `sales`

| Column | Description |
|---|---|
| sale_id | Primary key for sale |
| sale_date | Date of sale |
| product_id | Foreign key referencing `products` |
| customer_id | Foreign key referencing `customers` |
| total | Sale amount |
| rating | Customer rating |

## 🔗 Table Relationships

```text
city
  │
  └── city_id
        │
        ▼
customers
  │
  └── customer_id
        │
        ▼
sales ◄──── products
        │        │
        └────────┘
```

## ▶️ How to Run the Project

### 1. Create a PostgreSQL database

Create a database in PostgreSQL/pgAdmin, for example:

```text
coffee_shop
```

### 2. Create the tables

Open:

```text
sql/01_create_tables.sql
```

Run the table-creation statements in PostgreSQL.

### 3. Import the CSV data

Import the files from the `data/` folder into the corresponding PostgreSQL tables in this order:

```text
city.csv
products.csv
customers.csv
sales.csv
```

The foreign-key relationships require the referenced tables to exist before importing dependent data.

### 4. Run the analysis

Open:

```text
sql/02_business_questions_answers.sql
```

Run the queries one by one in pgAdmin to reproduce the analysis.

## 📊 Analysis Focus

The project focuses on questions a business could ask about its coffee market:

- Where is the estimated coffee-consumer population largest?
- How much revenue was generated in Q4 2023?
- Which products have the most sales?
- How does revenue differ across cities?
- How many unique customers are represented in each city?
- Which products perform best in each city?
- How are monthly sales changing?
- How do sales and estimated rent compare?
- Which city-level metrics can be combined for market-potential analysis?

## 📈 Portfolio Skills Demonstrated

This project demonstrates the ability to take a relational dataset and turn it into business-focused SQL analysis. It is particularly useful for demonstrating:

- Data extraction and filtering
- Data aggregation
- Relational joins
- Customer and revenue metrics
- Product performance analysis
- Time-series analysis
- Window functions
- CTE-based analytical queries
- Translating business questions into SQL

## ⚠️ Data Note

The repository currently contains the project datasets and SQL files used for the analysis. Check the CSV row counts after cloning/importing if you need to reproduce the complete source dataset exactly.

## 👤 Author

**Yash Sharma**

BCA Graduate | Aspiring Data Analyst

GitHub: [yash6677sharma-spec](https://github.com/yash6677sharma-spec)
