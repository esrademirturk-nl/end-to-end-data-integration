# End-to-End Data Integration & Analytics Project
### MySQL → Snowflake → MongoDB ETL Pipeline

## Project Overview
This project simulates a real-world data engineering pipeline using the Sakila film rental database. 
Data flows across three major platforms: MySQL, Snowflake, and MongoDB.

## Architecture
MySQL (Relational) → Export CSV → Snowflake (Cloud DW) → Transform → MongoDB (NoSQL)

## Tools & Technologies
| Platform | Tool | Purpose |
|---|---|---|
| MySQL | DBeaver | Relational database & SQL queries |
| Snowflake | Snowsight | Cloud data warehouse & analytics |
| MongoDB | Atlas & Compass | NoSQL document store & aggregations |

## Project Phases

### Phase 1 – MySQL
- Imported Sakila database (schema + data)
- Created ERD diagram
- Wrote 5 analytical SQL queries
- Exported customer, rental, payment tables as CSV

### Phase 2 – Snowflake
- Created warehouse, database and schema
- Loaded CSV files using Snowflake Ingestion
- Ran 3 analytical queries (monthly revenue, top customers, daily rentals)

### Phase 3 – MongoDB
- Created Atlas cluster and imported CSV collections
- Designed document structure
- Wrote 3 aggregation pipelines

## Key Findings
- Most rented film: Bucket Brotherhood (34 rentals)
- Top customer by spending: Karl Seal ($221.55)
- Most active country: India (1,572 rentals)
- Peak rental day: 2005-08-21 (659 rentals)
- Top revenue month: July 2005 ($28,368)

## Dataset
[Sakila Sample Database](https://dev.mysql.com/doc/sakila/en/) — MySQL official sample database
