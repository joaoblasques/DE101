# DE101 Exercises & Projects Structure

**Course:** Data Engineering 101
**Purpose:** Hands-on practice for each chapter
**Organization:** Chapter-based exercises + Capstone project

---

## Exercise Philosophy

**Progressive Difficulty:**
- Start with guided exercises
- Progress to independent challenges
- End with real-world scenarios

**Learning Approach:**
- Learn by doing, not just reading
- Make mistakes in a safe environment
- Build muscle memory through repetition

**Exercise Format:**
```
/Exercises/
├── Chapter_01/
│   ├── ex_1_lifecycle_mapping.md
│   ├── ex_2_role_comparison.md
│   └── ex_3_modern_stack_research.md
├── Chapter_02/
│   ├── ex_1_git_basics.md
│   ├── ex_2_branching_merging.md
│   └── ...
```

---

## Complete Exercises List

### Chapter 1: Introduction to Data Engineering (3 exercises)
1. Data Engineering Lifecycle Mapping
2. Role Comparison Analysis
3. Modern Data Stack Research

### Chapter 2: Version Control & Collaboration (5 exercises)
1. Git Repository Setup
2. Branching and Merging Practice
3. Pull Request Workflow
4. Documentation Writing
5. Basic CI/CD Pipeline

### Chapter 3: Linux & Command Line (6 exercises)
1. File Navigation and Manipulation
2. Text Processing with grep/sed/awk
3. Shell Script for Data Processing
4. Cron Job Scheduling
5. SSH and Remote Connections
6. Environment Configuration

### Chapter 4: Python Foundations (10 exercises)
1. Data Structures Practice
2. Control Flow Challenges
3. Function Writing
4. Class Implementation
5. File I/O Operations
6. Error Handling
7. Module Creation
8. Virtual Environment Setup
9. CSV Processing Script
10. Mini ETL Pipeline

### Chapter 5: SQL Fundamentals (15 exercises)
1. SELECT Basics
2. Filtering with WHERE
3. Aggregate Functions
4. GROUP BY Challenges
5. JOIN Types Practice
6. Subqueries
7. CTEs (Common Table Expressions)
8. Window Functions
9. CASE Statements
10. Date/Time Operations
11. String Manipulation
12. NULL Handling
13. Set Operations
14. Query Optimization
15. Comprehensive SQL Challenge

### Chapter 6: Database Systems (4 exercises)
1. PostgreSQL Setup and Schema Design
2. OLTP vs OLAP Analysis
3. MongoDB Document Modeling
4. Database Performance Comparison

### Chapter 7: Data Modeling (3 exercises)
1. Star Schema Design
2. Slowly Changing Dimensions
3. Data Model Comparison

### Chapter 8: Data Warehouses & Lakes (2 exercises)
1. File Format Comparison
2. Medallion Architecture Design

### Chapter 9: Data Architecture (2 exercises)
1. Architecture Design Document
2. Architecture Decision Records (ADRs)

### Chapter 10: Python Transformations (8 exercises)
1. Pandas Basics
2. Data Cleaning
3. Filtering and Sorting
4. Grouping and Aggregation
5. DataFrame Joins
6. Missing Data Handling
7. ETL Pipeline Building
8. Performance Optimization

### Chapter 11: dbt Transformations (6 exercises)
1. dbt Project Setup
2. Source and Staging Models
3. Incremental Models
4. Testing Framework
5. Documentation Generation
6. Production Deployment

### Chapter 12: Data Pipelines (5 exercises)
1. API Ingestion Pipeline
2. Web Scraping Script
3. Error Handling Implementation
4. Batch Processing Pipeline
5. Backfilling Strategy

### Chapter 13: Airflow Orchestration (7 exercises)
1. First DAG Creation
2. Task Dependencies
3. Scheduling Configuration
4. XCom Usage
5. Sensors Implementation
6. Error Handling in DAGs
7. End-to-End Orchestrated Pipeline

### Chapter 14: Docker Containerization (5 exercises)
1. Dockerfile Creation
2. Multi-Container Setup
3. Docker Compose Configuration
4. Containerized Python App
5. Containerized Data Pipeline

### Chapter 15: Production Best Practices (4 exercises)
1. Data Quality Test Suite
2. Monitoring Dashboard
3. Incident Response Runbook
4. CI/CD Pipeline Implementation

---

## Mini-Projects

### Mini-Project 1: CSV Data Processor (After Chapter 4)
**Duration:** 4-6 hours

**Objective:** Build a reusable Python utility for CSV processing

**Requirements:**
- Read CSV files from a directory
- Validate data quality (missing values, data types, ranges)
- Clean and standardize data
- Handle errors gracefully
- Log all operations
- Output clean CSV files

**Skills Practiced:**
- Python file I/O
- Error handling
- Logging
- Data validation
- Code organization

**Deliverables:**
- Python package with main script
- Configuration file
- README with usage instructions
- Test CSV files
- Log files

---

### Mini-Project 2: Database Design & Queries (After Chapter 6)
**Duration:** 6-8 hours

**Objective:** Design and implement a database for a business use case

**Scenario:** Online Bookstore Database

**Requirements:**
- Design ER diagram
- Implement schema in PostgreSQL
- Create tables with proper constraints
- Insert sample data (at least 100 books, 50 customers, 200 orders)
- Write 10 complex analytical queries:
  1. Top-selling books by category
  2. Customer lifetime value
  3. Monthly revenue trends
  4. Inventory levels
  5. Average order value
  6. Customer purchase patterns
  7. Book rating analysis
  8. Seasonal trends
  9. Author performance
  10. Recommendations based on purchase history

**Skills Practiced:**
- Database design
- Schema implementation
- SQL queries
- Data analysis

**Deliverables:**
- ER diagram
- SQL schema file
- Data generation script
- Query library
- Analysis report

---

### Mini-Project 3: Data Architecture Document (After Chapter 9)
**Duration:** 5-7 hours

**Objective:** Design a complete data architecture for a use case

**Scenario:** Choose one:
1. E-commerce analytics platform
2. SaaS product metrics dashboard
3. IoT sensor data processing
4. Social media analytics

**Requirements:**
- System architecture diagram
- Data flow diagrams
- Technology stack decisions
- Architecture Decision Records (ADRs)
- Cost estimation
- Scalability plan
- Security considerations
- Disaster recovery plan

**Skills Practiced:**
- Systems thinking
- Architecture design
- Documentation
- Trade-off analysis

**Deliverables:**
- Architecture document (10-15 pages)
- Diagrams (architecture, data flow, deployment)
- ADRs (3-5 decisions)
- Presentation slides

---

### Mini-Project 4: dbt Analytics Project (After Chapter 11)
**Duration:** 8-10 hours

**Objective:** Build a complete dbt project with best practices

**Scenario:** Subscription Business Analytics

**Requirements:**
- Source data: PostgreSQL tables (subscriptions, payments, users)
- Staging models for each source
- Intermediate models for business logic
- Mart models (star schema):
  - Fact: subscription_events
  - Dimensions: users, plans, payment_methods, dates
- Incremental models where appropriate
- At least 10 schema tests
- At least 5 custom data tests
- Complete documentation
- Generated docs site

**Skills Practiced:**
- dbt modeling
- SQL transformations
- Testing
- Documentation
- Project organization

**Deliverables:**
- dbt project repository
- README with setup instructions
- SQL models (staging, intermediate, marts)
- Tests (schema and data)
- Documentation
- dbt docs site

---

### Mini-Project 5: Orchestrated Data Pipeline (After Chapter 13)
**Duration:** 10-12 hours

**Objective:** Build an end-to-end orchestrated data pipeline

**Scenario:** Daily Weather Data Pipeline

**Requirements:**
- **Ingestion:** Fetch data from OpenWeather API
- **Storage:** Load raw data to PostgreSQL
- **Transformation:** Clean, aggregate, and enrich data
- **Quality:** Data validation checks
- **Orchestration:** Airflow DAG with:
  - Data ingestion task
  - Data validation task
  - Transformation tasks
  - Quality checks
  - Alerting on failures
- **Monitoring:** Airflow UI monitoring
- **Scheduling:** Daily at 6 AM UTC

**Skills Practiced:**
- API integration
- Pipeline design
- Airflow orchestration
- Error handling
- Monitoring

**Deliverables:**
- Airflow DAG file
- Python scripts for each task
- SQL transformation queries
- Configuration files
- Docker Compose setup
- README with instructions

---

## Capstone Project: E-Commerce Analytics Platform

### Overview
**Duration:** 15-20 hours  
**Difficulty:** Advanced  
**Integration:** All course concepts

### Business Context
You're the data engineer for "DataMart," a growing e-commerce company. They need a complete analytics platform to:
- Track daily sales performance
- Analyze customer behavior and segments
- Monitor product inventory
- Generate executive dashboards
- Enable data-driven decisions

### Project Requirements

#### 1. Data Sources
**Multiple source types:**
- **API:** Sales transactions (mock REST API or use Faker to generate)
- **CSV Files:** Product catalog, customer data
- **Database:** Inventory management (PostgreSQL)

**Data Volume:**
- 10,000+ products
- 50,000+ customers
- 500,000+ transactions
- Daily new data

#### 2. Data Ingestion
**Tools:** Python + Airflow

**Pipelines:**
- API ingestion (sales data every hour)
- File watcher (new CSV files daily)
- Database CDC (inventory changes)

**Requirements:**
- Error handling and retries
- Data validation at ingestion
- Idempotent operations
- Logging all operations

#### 3. Data Storage
**Architecture:** Data Lakehouse approach

**Layers:**
- **Bronze (Raw):** Unprocessed data from sources
  - Format: JSON, CSV, raw dumps
  - Storage: Local filesystem or S3
- **Silver (Cleansed):** Validated, cleaned data
  - Format: Parquet
  - Schema: Enforced
- **Gold (Curated):** Business-ready dimensional models
  - Format: PostgreSQL tables
  - Schema: Star schema

#### 4. Data Transformation
**Tool:** dbt

**Data Models:**

**Staging Layer:**
- `stg_sales_transactions`
- `stg_products`
- `stg_customers`
- `stg_inventory`

**Intermediate Layer:**
- `int_customer_lifetime_value`
- `int_product_performance`
- `int_daily_aggregates`

**Marts Layer:**
- **Fact Tables:**
  - `fact_sales` (grain: transaction line item)
  - `fact_inventory_snapshots` (grain: daily product snapshot)
- **Dimension Tables:**
  - `dim_customers` (SCD Type 2)
  - `dim_products`
  - `dim_dates`
  - `dim_locations`

**Testing:**
- Minimum 20 schema tests
- 10 custom data quality tests
- Freshness checks
- Relationship tests

#### 5. Orchestration
**Tool:** Apache Airflow

**DAGs:**

**1. Daily Sales Pipeline:**
```
extract_sales_api → validate_sales → load_bronze →
transform_silver → dbt_staging → dbt_marts →
quality_checks → send_summary_email
```

**2. Weekly Customer Sync:**
```
extract_customer_csv → validate_customers →
load_bronze → transform_silver →
dbt_customer_dimensions → quality_checks
```

**3. Hourly Inventory Updates:**
```
check_inventory_changes → extract_changes →
load_bronze → update_silver → refresh_facts
```

**Scheduling:**
- Daily Sales: 7 AM UTC daily
- Weekly Sync: Sunday 2 AM UTC
- Inventory: Every hour
- Backfilling capabilities

#### 6. Data Quality
**Frameworks:** dbt tests + Great Expectations (bonus)

**Quality Dimensions:**
- **Completeness:** No null values in required fields
- **Accuracy:** Values within expected ranges
- **Consistency:** Relationships maintained
- **Timeliness:** Data freshness checks
- **Uniqueness:** No duplicates in fact tables

**Tests:**
- Row count comparisons (source vs target)
- Sum reconciliation
- Referential integrity
- Business rule validation
- Outlier detection

#### 7. Monitoring & Logging
**Components:**
- Airflow UI for DAG monitoring
- Python logging (structured logs)
- Custom dashboard for pipeline health
- Alerts on failures (email or Slack)

**Metrics Tracked:**
- Pipeline run duration
- Data volumes processed
- Error rates
- Test pass/fail rates
- Data freshness

#### 8. Containerization
**Tool:** Docker + Docker Compose

**Services:**
- PostgreSQL (database)
- Airflow (webserver, scheduler, worker)
- dbt (as Airflow task)
- Custom Python apps

**Configuration:**
- Multi-container setup
- Environment variables
- Volume mounts for persistence
- Network configuration

#### 9. Version Control & Documentation
**Repository Structure:**
```
ecommerce-analytics-platform/
├── README.md
├── docs/
│   ├── architecture.md
│   ├── data_dictionary.md
│   ├── setup_guide.md
│   └── diagrams/
├── airflow/
│   ├── dags/
│   ├── plugins/
│   └── config/
├── dbt/
│   ├── models/
│   ├── tests/
│   ├── macros/
│   └── dbt_project.yml
├── src/
│   ├── ingestion/
│   ├── utils/
│   └── tests/
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── data/
│   ├── bronze/
│   ├── silver/
│   └── gold/
├── scripts/
│   ├── setup_db.sql
│   ├── generate_data.py
│   └── run_tests.sh
├── tests/
└── .gitignore
```

**Documentation:**
- Comprehensive README
- Architecture diagrams
- Data flow diagrams
- API documentation
- Setup instructions
- Troubleshooting guide
- Data dictionary

#### 10. Demo & Presentation
**Create:**
- 10-minute demo video walkthrough
- Presentation slides (10-15 slides)
- Live demo (optional)

**Cover:**
- Problem statement
- Architecture overview
- Tech stack justification
- Key features
- Data pipeline flow
- Dashboard showcase
- Challenges faced
- Lessons learned
- Future improvements

### Deliverables Checklist

**Code & Configuration:**
- [ ] GitHub repository (public or private)
- [ ] All source code
- [ ] Docker configuration
- [ ] Airflow DAGs
- [ ] dbt project
- [ ] SQL scripts

**Documentation:**
- [ ] Comprehensive README
- [ ] Architecture document
- [ ] Setup guide
- [ ] Data dictionary
- [ ] API documentation

**Diagrams:**
- [ ] System architecture
- [ ] Data flow diagram
- [ ] ERD (Entity-Relationship Diagram)
- [ ] Star schema diagram
- [ ] Deployment diagram

**Evidence:**
- [ ] Screenshots of working pipelines
- [ ] Airflow DAG runs
- [ ] dbt docs site
- [ ] Data quality test results
- [ ] Sample queries and results

**Presentation:**
- [ ] Demo video or slides
- [ ] Project highlights
- [ ] Technical decisions explained

### Evaluation Criteria

**Technical Implementation (50%):**
- Code quality and organization
- Proper use of tools (Airflow, dbt, Docker)
- Data pipeline design
- Error handling
- Testing coverage

**Architecture & Design (20%):**
- System architecture decisions
- Data modeling quality
- Scalability considerations
- Best practices followed

**Documentation (15%):**
- README quality
- Code comments
- Architecture documentation
- Setup instructions

**Data Quality (10%):**
- Testing coverage
- Data validation
- Quality checks
- Monitoring

**Presentation (5%):**
- Communication clarity
- Demo quality
- Problem articulation

### Bonus Features
- Real-time streaming pipeline (Kafka)
- Dashboard with BI tool (Metabase, Superset)
- Great Expectations integration
- Terraform infrastructure
- Kubernetes deployment
- Data catalog (DataHub, Amundsen)
- Machine learning feature store

### Timeline
**Week 1:** Setup + Ingestion
**Week 2:** Transformation + Data Modeling
**Week 3:** Orchestration + Quality
**Week 4:** Containerization + Documentation
**Week 5:** Testing + Demo

---

## Project Submission Guidelines

### GitHub Repository
- Public repository (or private with access granted)
- Clean git history with meaningful commits
- Proper .gitignore (no secrets, no large files)
- Tagged releases (v1.0.0)

### README Template
```markdown
# Project Name

Brief description

## Architecture

[Diagram]

## Tech Stack

- List all technologies used

## Setup Instructions

Step-by-step guide

## Project Structure

Directory breakdown

## Data Pipeline

How it works

## Running the Project

Commands to execute

## Testing

How to run tests

## Demo

Link to video/screenshots

## Lessons Learned

Key takeaways

## Future Improvements

What's next
```

### Documentation Standards
- Clear, concise writing
- Diagrams where helpful
- Code examples
- Screenshots/GIFs
- Links to resources

---

## Additional Practice Resources

### Datasets
- Kaggle datasets
- Public APIs (OpenWeather, GitHub, Reddit)
- Mock data generators (Faker, Mockaroo)
- Sample datasets (Northwind, AdventureWorks)

### Platforms
- DataCamp Projects
- HackerRank SQL
- LeetCode Database
- Kaggle Competitions
- Mode Analytics SQL Tutorial

### Communities
- r/dataengineering
- dbt Community Slack
- Data Talks Club
- Locally Optimistic
- Data Engineering Discord

---

*Created: 2025-10-19*
*Status: Exercise framework complete*
*Next: Develop individual exercise files*
