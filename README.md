# 🎬 End-to-End Data Integration & Analytics Project
### From a Film Rental Store to a Modern Data Pipeline

> *Imagine a film rental company — thousands of customers, millions of transactions, and a mountain of data.*
> *This project takes that raw data and transforms it into insights using three powerful platforms.*

---

## 🗺️ The Journey

```
🐬 MySQL          ──► 📄 CSV Export ──►   ❄️ Snowflake        ──►   🍃 MongoDB
(Relational DB)                         (Cloud Warehouse)           (NoSQL Store)
   OLTP                                      OLAP                    Document DB
"Store it right"                        "Analyze it fast"         "Scale it freely"
```

---

## 🎯 The Mission

The **Sakila** database is MySQL's official sample dataset — a fictional film rental company with customers, films, rentals, payments, and staff across multiple stores worldwide.

Our goal: **migrate, transform, and analyze** this data across three platforms — experiencing firsthand how real-world data engineering pipelines work.

---

## 🔹 Phase 1 — MySQL: Where the Data Lives

> *"Every great journey begins with raw data."*

MySQL is the **source of truth** — the operational database where all business transactions are recorded in real time.

### What we did:
- 📥 Imported the full Sakila database (23 tables, schema + data)
- 🗺️ Built an **ERD diagram** to visualize all table relationships
- 🔍 Wrote **5 analytical SQL queries** to explore the data
- 📤 Exported `customer`, `rental`, `payment` tables as CSV files

### Key findings from SQL queries:

| # | Query | Top Result |
|---|-------|------------|
| 1 | Most rented film | 🎬 Bucket Brotherhood — 34 rentals |
| 2 | Top spending customer | 💳 Karl Seal — $221.55 |
| 3 | Films by category | 🏆 Sports — 74 films |
| 4 | Rentals by country | 🌍 India — 1,572 rentals |
| 5 | Monthly revenue (2005) | 📈 July — $28,368 |

### Tools used:
- 🐬 **MySQL 8.0** — Relational database engine
- 🦫 **DBeaver** — Universal SQL client (used instead of MySQL Workbench due to macOS compatibility)

---

## 🔹 Phase 2 — Snowflake: Where the Data Gets Analyzed

> *"Clean data in, powerful insights out."*

Snowflake is a **cloud data warehouse** built for analytics. Unlike MySQL, it's designed to handle massive datasets and complex aggregation queries at lightning speed.

### What we did:
- ❄️ Created a Snowflake account, warehouse (`SAKILA_WH`), database (`SAKILA_DB`), and schema (`SAKILA_SCHEMA`)
- 📥 Loaded CSV files using **Snowflake Ingestion**
- 📊 Ran **3 analytical queries** with chart visualizations

### Analytical queries:

| # | Query | Insight |
|---|-------|---------|
| 1 | Monthly revenue (2005) | July was peak month with $28,368 |
| 2 | Top 10 customers by payment | Customer #526 spent the most |
| 3 | Daily rental count | Aug 21, 2005 was the busiest day (659 rentals) |

### Tools used:
- ❄️ **Snowflake** — Cloud data warehouse
- 🌐 **Snowsight** — Web-based SQL editor with built-in charts

---

## 🔹 Phase 3 — MongoDB: Where the Data Becomes Flexible

> *"Not all data fits neatly in a table — and that's okay."*

MongoDB is a **NoSQL document store** — instead of rows and columns, data is stored as JSON-like documents. It's perfect for flexible schemas, nested data, and horizontal scaling.

### What we did:
- 🌿 Created a **MongoDB Atlas** cloud cluster
- 📥 Imported CSV files as collections (`customers`, `rentals`, `payments`)
- 🔍 Built **3 aggregation pipelines** to analyze the data

### Aggregation pipelines:

| # | Pipeline | Result |
|---|----------|--------|
| 1 | Rentals per customer | Customer #148 — 46 rentals (top) |
| 2 | Total payments per customer | Customer #526 — highest spender |
| 3 | Rentals by staff | Staff #1: 8,040 · Staff #2: 8,004 |

### Tools used:
- 🍃 **MongoDB Atlas** — Cloud NoSQL cluster
- 🧭 **MongoDB Compass** — Visual database explorer

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    SAKILA DATABASE                          │
│                 (Film Rental Company)                       │
└───────────────────────┬─────────────────────────────────────┘
                        │
              ┌─────────▼─────────┐
              │   🐬 MySQL 8.0    │  ← OLTP: Operational Data
              │  23 Tables · ERD  │
              │  5 SQL Queries    │
              └─────────┬─────────┘
                        │ CSV Export
              ┌─────────▼─────────┐
              │  ❄️ Snowflake     │  ← OLAP: Analytics & Reporting
              │  Cloud Warehouse  │
              │  3 Queries+Charts │
              └─────────┬─────────┘
                        │ JSON Documents
              ┌─────────▼─────────┐
              │  🍃 MongoDB       │  ← NoSQL: Flexible Storage
              │  Atlas Cluster    │
              │  3 Aggregations   │
              └───────────────────┘
```

---

## 📊 Key Comparisons

| Feature | 🐬 MySQL | ❄️ Snowflake | 🍃 MongoDB |
|---------|----------|--------------|-----------|
| Type | Relational (OLTP) | Cloud DW (OLAP) | Document (NoSQL) |
| Schema | Fixed | Fixed | Flexible |
| Best for | Transactions | Analytics | Unstructured data |
| Query language | SQL | SQL | Aggregation Pipeline |
| Scaling | Vertical | Horizontal (cloud) | Horizontal |
| Use case | Daily operations | Business intelligence | Flexible apps |

---

## 💡 Reflection

This project taught me that **data engineering is not just about storing data — it's about moving it to where it can create the most value.**

MySQL excels at maintaining data integrity for real-time operations, but struggles with complex analytical workloads. Snowflake's cloud architecture makes large-scale aggregations feel effortless, separating compute from storage for maximum flexibility. MongoDB's document model shows how modern applications benefit from schema freedom — especially when data structures evolve over time.

The most valuable lesson: **no single database fits all use cases.** A mature data architecture combines multiple systems, each doing what it does best.

---

## 📁 Project Structure

```
📦 end-to-end-data-integration
 ┣ 📄 mysql_queries.sql          ← Phase 1: MySQL analytical queries
 ┣ 📄 snowflake_queries.sql      ← Phase 2: Snowflake queries
 ┣ 📄 mongodb_aggregations.json  ← Phase 3: MongoDB pipelines
 ┣ 🖼️ sakila.png                 ← ERD diagram
 ┣ 📸 screenshots/               ← Query results from all platforms
 ┗ 📄 README.md                  ← This file
```

---

## 🎓 Learning Outcomes

By completing this project, I gained hands-on experience with:

- ✅ Designing and documenting relational databases (ERD)
- ✅ Writing complex SQL queries (JOINs, GROUP BY, HAVING, subqueries)
- ✅ ETL workflows across multiple platforms
- ✅ Cloud data warehousing with Snowflake
- ✅ NoSQL document modeling and aggregation pipelines
- ✅ Understanding OLTP vs OLAP vs NoSQL architectures

---

## 🛠️ Tech Stack

![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?logo=mysql)
![Snowflake](https://img.shields.io/badge/Snowflake-Cloud-29B5E8?logo=snowflake)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?logo=mongodb)
![DBeaver](https://img.shields.io/badge/DBeaver-Community-brown)

---

*Built as part of the VIT (Voorbereiding IT) program at We'RHERE Academy — Data Engineering Module*
