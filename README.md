# PySpark & DBT Analytics Pipeline  
**End-to-End Data Engineering Project | Medallion Architecture | Delta Lake | SCD Type 2**  
[![Project Report](https://img.shields.io/badge/Report-View%20Details-blue)]()


Production-grade analytics pipeline built on **Databricks Community Edition**, demonstrating modern data engineering and analytics engineering best practices using a pseudo-Uber dataset.

---

## Project Overview

This project implements a complete **end-to-end data engineering pipeline** that ingests raw CSV data, processes it incrementally using **PySpark**, and models analytics-ready datasets using **DBT**. The pipeline follows the **Medallion Architecture (Bronze → Silver → Gold)** and supports **Slowly Changing Dimensions (SCD Type 2)** for full historical tracking.

Key objectives of the project include:
- Incremental ingestion with fault tolerance
- Clean, deduplicated, and upserted silver tables
- Dimensional modeling with DBT
- Analytics-ready fact, dimension tables, and BI views
- Idempotent, modular, and production-ready design patterns

---

## Tech Stack

**PySpark** • **DBT (Cloud)** • **Delta Lake** • **Databricks** • **Python** • **SQL** • **Jinja** • **Git** • **YAML**

---

## Key Features

✅ **Incremental ingestion** using PySpark Structured Streaming  
✅ **Exactly-once processing** with checkpointing and idempotent design  
✅ **Dynamic schema inference** to avoid hardcoded schemas  
✅ **Advanced deduplication** using window functions and hashing  
✅ **Conditional upserts** via Delta Lake merge operations  
✅ **SCD Type 2** implementation using DBT snapshots  
✅ **Modular Python transformations** using OOP principles  
✅ **Analytics-ready BI views** built on a star schema  

---

## Dataset

Pseudo-Uber ride-sharing dataset stored as CSV files, including:

- **Trips** – ride details, timestamps, distances, fares  
- **Customers** – rider profiles, contact details  
- **Drivers** – driver attributes and ratings  
- **Vehicles** – fleet information  
- **Payments** – transaction records and payment types  
- **Locations** – pickup and dropoff zones  

---

## Architecture Highlights

### Bronze Layer
- Incremental ingestion from CSV files using **PySpark Structured Streaming**
- Automatic schema inference
- One-time micro-batch execution using `trigger(once=True)`
- Checkpointing for fault tolerance and exactly-once processing
- Raw data stored as Delta tables in the bronze schema

---

### Silver Layer
- Modular transformations implemented via a reusable **Python Transformations class**
- Data cleaning using:
  - Regex operations
  - Conditional logic
  - String standardization
- Deduplication using window functions and hash keys
- Incremental **Delta merge (upserts)** based on CDC timestamps
- Audit columns (`process_timestamp`) for governance and traceability

---

### Gold Layer
- Modeled using **DBT Cloud**
- Incremental DBT models with **Jinja templating**
- Clean source definitions for lineage tracking
- **Star schema** with fact and dimension tables
- **SCD Type 2** implemented using DBT snapshots
- Final **analytics-ready views** for BI consumption

---

## BI & Analytics Views

Three production-ready SQL views were created in the gold schema:

1. **vw_top_drivers_by_revenue**  
   - Top drivers by total fare
   - Trip counts and average ratings

2. **vw_customer_lifetime_value**  
   - Customer LTV
   - Trip frequency and recency metrics

3. **vw_city_payment_performance**  
   - Payment success rates by city
   - 3-month rolling average fares

These views abstract complex joins and provide clean datasets for BI tools such as **Power BI**.

---

## Skills Demonstrated

### Data Engineering
- PySpark Structured Streaming
- Incremental and idempotent pipeline design
- Medallion architecture implementation
- Delta Lake ACID transactions and merge logic

### Development Practices
- Object-oriented Python for reusable transformations
- Modular, scalable notebook design
- Git-based version control
- Cost-aware design using Databricks Community Edition

### Analytics Engineering & Data Modeling
- DBT sources, models, snapshots, and tests
- Incremental materializations
- SCD Type 2 dimensional modeling
- Dynamic SQL generation using Jinja
- Lineage, documentation, and governance best practices
