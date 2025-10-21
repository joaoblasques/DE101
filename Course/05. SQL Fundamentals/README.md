# Chapter 05: SQL Fundamentals & Relational Databases

**Part:** II - Database & Data Modeling
**Duration:** 12-15 hours
**Exercises:** 15 SQL challenges
**Prerequisites:** Chapter 4 (Python Foundations)

---

## =Ë Chapter Overview

Master the art of querying and manipulating data using SQL. This chapter covers everything from basic SELECT statements to advanced window functions, preparing you to work with any relational database system.

SQL is the foundation of data engineering - you'll use it daily regardless of your specific role. Whether you're building ETL pipelines, analyzing data quality, or designing data warehouses, SQL is your primary tool for interacting with data.

This chapter ensures you can write efficient, readable SQL that handles complex analytical queries. You'll learn not just the syntax, but the underlying concepts of relational databases, query optimization, and best practices that will make you a proficient data engineer.

**What You'll Build:**
- Complex multi-table analytical queries answering real business questions
- Performance-optimized queries using indexes and execution plans
- Data quality validation queries for pipeline monitoring
- Real-world analytics scenarios (cohort analysis, funnel analysis, time-series)

---

## <¯ Learning Objectives

After completing this chapter, you will be able to:
- Write complex SQL queries for data analysis and transformation
- Master JOINs to combine data from multiple tables effectively
- Use aggregate functions and GROUP BY for analytical queries
- Apply window functions for advanced analytics (rankings, running totals, LAG/LEAD)
- Optimize query performance using indexes, execution plans, and best practices
- Understand relational database concepts (ACID, normalization, primary/foreign keys)
- Handle NULL values and edge cases gracefully
- Work with dates, times, and string data confidently
- Write maintainable, documented SQL code following industry standards

---

## =Ú Subchapters

### 01. Introduction to Relational Databases
**Time:** 45 minutes
**Key Concepts:** ACID properties, tables, schemas, database design principles, transactions

Learn the foundational concepts of relational databases that underpin all SQL work. Understand why relational databases remain the backbone of most data systems.

---

### 02. SQL Basics - SELECT, WHERE, ORDER BY
**Time:** 1.5 hours
**Key Concepts:** Filtering, sorting, basic queries, LIMIT, DISTINCT

**File:** `02. SQL Basics - SELECT, WHERE, ORDER BY.md`

Master the fundamental SQL statements you'll use in every query. Learn to filter data precisely and sort results meaningfully.

**Content Source:** `Resources/Legacy-Content/1. SQL/01. SQL Basics - Quick Reference.md`

---

### 03. Filtering and Logical Operators
**Time:** 1 hour
**Key Concepts:** AND, OR, NOT, IN, BETWEEN, LIKE, NULL handling

**File:** `03. Filtering and Logical Operators.md`

Build complex filtering logic to extract exactly the data you need. Master pattern matching and logical operators.

**Content Source:** `Resources/Legacy-Content/1. SQL/01. SQL Basics - Quick Reference.md`

---

### 04. Aggregate Functions
**Time:** 1.5 hours
**Key Concepts:** COUNT, SUM, AVG, MIN, MAX, DISTINCT

**File:** `04. Aggregate Functions.md`

Summarize and analyze data using SQL's built-in aggregation capabilities. Essential for any analytical work.

---

### 05. GROUP BY and HAVING
**Time:** 2 hours
**Key Concepts:** Grouping data, filtering aggregates, ROLLUP, CUBE

**File:** `05. GROUP BY and HAVING.md`

Group data by dimensions and apply aggregate metrics - the foundation of analytics and reporting.

---

### 06. JOINs - Combining Tables
**Time:** 2 hours
**Key Concepts:** INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN, CROSS JOIN, self-joins

**File:** `06. JOINs - Combining Tables.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/06. Advanced Join Patterns.md`

Combine data from multiple tables to answer complex business questions. Master the most important concept in SQL.

---

### 07. Subqueries and CTEs
**Time:** 1.5 hours
**Key Concepts:** Nested queries, Common Table Expressions, WITH clause, recursive CTEs

**File:** `07. Subqueries and CTEs.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/07. CTEs - Common Table Expressions.md`

Break down complex queries into readable, maintainable components using CTEs. Write SQL that your teammates will thank you for.

---

### 08. Window Functions
**Time:** 2 hours
**Key Concepts:** ROW_NUMBER, RANK, DENSE_RANK, LAG, LEAD, OVER, PARTITION BY, running totals

**File:** `08. Window Functions.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/08. Window Functions - Advanced SQL Analytics.md`

Perform advanced analytics like running totals, rankings, and comparisons across rows. Essential for time-series analysis and cohort studies.

---

### 09. CASE Statements and Conditional Logic
**Time:** 1 hour
**Key Concepts:** CASE WHEN, COALESCE, NULLIF, conditional aggregations, pivoting

**File:** `09. CASE Statements and Conditional Logic.md`

Add conditional logic to your queries for dynamic transformations and data categorization.

---

### 10. Set Operations
**Time:** 45 minutes
**Key Concepts:** UNION, UNION ALL, INTERSECT, EXCEPT, combining query results

**File:** `10. Set Operations.md`

Combine results from multiple queries using set theory operations.

---

### 11. String Functions and Pattern Matching
**Time:** 1.5 hours
**Key Concepts:** CONCAT, SUBSTRING, UPPER, LOWER, TRIM, REGEXP, LIKE, string parsing

**File:** `11. String Functions and Pattern Matching.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/04. String Manipulation & Pattern Matching.md`

Manipulate text data for cleaning, formatting, and extraction. Critical for working with real-world messy data.

---

### 12. Date and Time Operations
**Time:** 1.5 hours
**Key Concepts:** DATE, TIMESTAMP, INTERVAL, date arithmetic, time zones, DATE_TRUNC, EXTRACT

**File:** `12. Date and Time Operations.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/05. Date & Time Operations.md`

Work with temporal data - critical for time-series analysis, event tracking, and understanding data freshness.

---

### 13. Working with NULL Values
**Time:** 45 minutes
**Key Concepts:** IS NULL, IS NOT NULL, COALESCE, NULLIF, NULL semantics in aggregations and JOINs

**File:** `13. Working with NULL Values.md`

Handle missing data correctly - a common source of bugs in production queries. Understand three-valued logic.

---

### 14. Query Optimization Basics
**Time:** 1.5 hours
**Key Concepts:** Indexes, EXPLAIN plans, query performance, execution order, best practices

**File:** `14. Query Optimization Basics.md`

**Content Source:** `Resources/Legacy-Content/1. SQL/12. SQL Indexes - Performance Optimization.md`
**Content Source:** `Resources/Legacy-Content/1. SQL/14. Query Optimization Techniques.md`

Write queries that scale - understand how databases execute queries and optimize accordingly.

---

### 15. Best Practices for Analytical SQL
**Time:** 1 hour
**Key Concepts:** Code style, readability, maintainability, testing, documentation

**File:** `15. Best Practices for Analytical SQL.md`

Write SQL that your teammates (and future you) will thank you for. Professional SQL standards.

---

## <Ë Chapter Exercises

**Location:** `Exercises/Chapter-05/`

### Exercise Set 1: Basic Queries (5 exercises)
- SELECT, WHERE, ORDER BY practice with e-commerce dataset
- Filtering with multiple conditions (AND, OR, IN, BETWEEN)
- Pattern matching with LIKE and REGEXP
- Working with DISTINCT and LIMIT

### Exercise Set 2: Aggregations (3 exercises)
- GROUP BY queries (sales by region, product category performance)
- HAVING clause filtering (find top performers)
- Complex aggregations (nested aggregations, conditional counts)

### Exercise Set 3: JOINs (4 exercises)
- Multi-table joins (customers, orders, products, order_items)
- Self-joins (finding related records)
- LEFT JOINs with NULL analysis (finding missing relationships)
- Join performance comparisons

### Exercise Set 4: Window Functions (3 exercises)
- Ranking queries (top N per group, percentiles)
- Running totals and moving averages
- LAG/LEAD comparisons (period-over-period analysis)

### Final Challenge: E-Commerce Analytics Dashboard
Build a complete analytical query combining:
- Multiple JOINs (4+ tables)
- CTEs for readability
- Window functions for rankings and running totals
- Aggregations for summary metrics
- Date filtering and time-based analysis

**Dataset:** Sample e-commerce data (customers, orders, products, order_items, categories)

**Deliverable:** Single SQL query that produces a comprehensive analytics report answering 10 business questions.

---

## <¯ Chapter Project

**Mini-Project 2: Database Analytics Report**

Build a comprehensive SQL analytics report for an e-commerce business using real-world data patterns.

**Requirements:**
1. **Design database schema** (customers, orders, products, order_items, reviews)
2. **Load sample data** (10K+ rows across tables)
3. **Write 10 analytical queries** answering business questions:
   - Revenue trends by month and category
   - Top customers by lifetime value (with ranking)
   - Product performance metrics (conversion rate, average rating)
   - Customer cohort analysis (retention by signup month)
   - Churn analysis (customers who haven't purchased in 90+ days)
   - Basket analysis (most commonly purchased together)
   - Sales funnel analysis (cart abandonment rate)
   - Geographic analysis (revenue by region/country)
   - Seasonal trends (best/worst selling periods)
   - Inventory analysis (low stock alerts)

4. **Optimize queries** (add indexes, analyze execution plans)
5. **Document findings** (insights and recommendations)

**Deliverables:**
- Schema design (ERD diagram)
- SQL scripts with documented queries
- Query optimization report (before/after performance)
- Business insights presentation (key findings)

**Time:** 4-6 hours

**Skills Practiced:** All SQL concepts from this chapter in a realistic business context

---

## =Ê Key Concepts Summary

### Relational Database Fundamentals
- **ACID properties:** Atomicity, Consistency, Isolation, Durability
- **Tables:** Rows (records) and columns (attributes)
- **Keys:** Primary keys (unique identifiers), Foreign keys (relationships)
- **Normalization:** 1NF, 2NF, 3NF (reducing redundancy)
- **Transactions:** Atomic units of work

### SQL Query Structure
```sql
SELECT [columns]           -- 5. Select columns to return
FROM [table]               -- 1. Specify table(s)
WHERE [filter conditions]  -- 2. Filter rows
GROUP BY [columns]         -- 3. Group rows
HAVING [aggregate filters] -- 4. Filter groups
ORDER BY [columns]         -- 6. Sort results
LIMIT [n];                 -- 7. Limit rows returned
```

### JOIN Types
- **INNER JOIN:** Matching rows only (intersection)
- **LEFT JOIN:** All left table rows + matches from right
- **RIGHT JOIN:** All right table rows + matches from left
- **FULL JOIN:** All rows from both tables
- **CROSS JOIN:** Cartesian product (all combinations)
- **SELF JOIN:** Join table to itself

### Aggregate Functions
- **COUNT(*):** Count all rows
- **COUNT(column):** Count non-NULL values
- **SUM(column):** Sum numeric values
- **AVG(column):** Average of numeric values
- **MIN/MAX(column):** Minimum/maximum values

### Window Functions
- **ROW_NUMBER():** Sequential number for each row
- **RANK():** Rank with gaps for ties
- **DENSE_RANK():** Rank without gaps
- **LAG/LEAD():** Access previous/next row values
- **SUM/AVG/COUNT() OVER():** Aggregate without collapsing rows

### Best Practices
1. **Always use table aliases** in multi-table queries
2. **Use CTEs for complex queries** (readability over nested subqueries)
3. **Indent and format SQL** for readability (standard style guide)
4. **Add comments** explaining business logic, not syntax
5. **Test queries on small datasets first** before production
6. **Use LIMIT during development** to avoid long-running queries
7. **Avoid SELECT *** in production (explicit column names)
8. **Use meaningful aliases** (descriptive, not a, b, c)
9. **Handle NULLs explicitly** (don't assume behavior)
10. **Consider performance** (indexes, execution plans, query structure)

---

## = Related Concepts

- [[Course/06. Database Systems/README|Chapter 6: Database Systems]] - Database types and selection
- [[Course/07. Data Modeling/README|Chapter 7: Data Modeling]] - Designing database schemas (star schema, dimensional modeling)
- [[Course/10. Python Transformations/README|Chapter 10: Python Transformations]] - SQL + Pandas for ETL
- [[Course/11. dbt Transformations/README|Chapter 11: dbt Transformations]] - SQL-based transformation workflows
- [[Course/15. Production Best Practices/README|Chapter 15: Production Best Practices]] - Data quality and validation with SQL
- [[Resources/Legacy-Content/1. SQL/|Legacy SQL Content]] - Original SQL learning materials (14 comprehensive notes)

---

## =Ú Additional Resources

### Documentation
- [PostgreSQL Documentation](https://www.postgresql.org/docs/) - Most comprehensive SQL reference
- [SQLBolt](https://sqlbolt.com/) - Interactive SQL tutorial
- [Mode SQL Tutorial](https://mode.com/sql-tutorial/) - Analytics-focused SQL guide
- [SQL Style Guide](https://www.sqlstyle.guide/) - Community SQL formatting standards

### Practice Platforms
- [LeetCode SQL](https://leetcode.com/problemset/database/) - 200+ SQL problems (easy to hard)
- [HackerRank SQL](https://www.hackerrank.com/domains/sql) - Structured SQL challenges
- [SQLZoo](https://sqlzoo.net/) - Interactive SQL exercises
- [DataLemur](https://datalemur.com/) - Real data science SQL interview questions

### Books
- **"SQL Antipatterns"** by Bill Karwin - Common mistakes and how to avoid them
- **"The Art of SQL"** by Stté

phane Faroult - Performance and elegance
- **"SQL for Data Analysis"** by Cathy Tanimura - Analytics-focused SQL techniques

### Video Tutorials
- [Stanford SQL Course](https://www.youtube.com/playlist?list=PLroEs25KGvwzmvIxYHRhoGTz9w8LeXek0) - Comprehensive SQL fundamentals
- [SQL Tutorial for Beginners](https://www.youtube.com/watch?v=HXV3zeQKqGY) - FreeCodeCamp (4 hours)

---

##  Chapter Completion Checklist

- [ ] Complete all 15 subchapters
- [ ] Finish all exercise sets (15 total exercises)
- [ ] Complete Mini-Project 2 (Database Analytics Report)
- [ ] Review key concepts and SQL query structure
- [ ] Practice on LeetCode/HackerRank (complete 10+ SQL problems)
- [ ] Can write complex multi-table queries confidently
- [ ] Understand query optimization basics (indexes, EXPLAIN)
- [ ] Can explain JOINs and when to use each type
- [ ] Comfortable with window functions for analytics
- [ ] Can handle NULL values and edge cases correctly

---

**Next Chapter:** [[Course/06. Database Systems/README|Chapter 6: Database Systems & Data Stores]]

---

*Created: October 21, 2025*
*Last Updated: October 21, 2025*
*Status: =Ý Chapter README complete - Creating subchapters next*
