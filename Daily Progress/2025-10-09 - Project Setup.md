# 2025-10-09 - SQL Basics (Chapter 1)

**Module:** Module 1 - SQL Data Transformation
**Time Spent:** ~2-3 hours
**Status:** ✅ Chapter 1 Complete (sections 1.1-1.4.5)

---

## 📝 Today's Goals

- [x] Set up Obsidian project structure
- [x] Clone course materials to working directory
- [x] Complete Chapter 1: SQL Basics (sections 1.1-1.4.5)
- [x] Set up development environment

## 💡 What I Learned

### 1. Spark Catalog Structure
- **Hierarchy:** `Catalog → Schema → Table`
- Use full path when referencing tables: `schema.table_name`
- Can set default schema with `USE schema_name` command
- Important for working with Spark SQL in data engineering pipelines

### 2. Basic SELECT Statements
```sql
-- Retrieve all columns
SELECT * FROM customer LIMIT 10;

-- Retrieve specific columns
SELECT c_name, c_acctbal, c_nationkey FROM customer;
```

### 3. WHERE Clause & Filtering
**Conditional Operators:**
- `<`, `>`, `<=`, `>=`, `=`, `<>` or `!=`

**Pattern Matching with LIKE:**
- `%` = zero or more characters
- `_` = any single character

```sql
-- Multiple conditions
SELECT * FROM customer
WHERE c_nationkey = 20
  AND c_acctbal > 1000;

-- Pattern matching
SELECT * FROM customer
WHERE c_name LIKE '%381%';
```

### 4. ORDER BY for Sorting
```sql
-- Default: ascending order
SELECT * FROM customer ORDER BY c_acctbal;

-- Descending order
SELECT * FROM customer ORDER BY c_acctbal DESC;
```

### 5. JOIN Types (5 Main Types)
1. **INNER JOIN** (default): Returns only matching rows from both tables
2. **LEFT OUTER JOIN**: All rows from left table + matching rows from right
3. **RIGHT OUTER JOIN**: Matching rows from left + all rows from right
4. **FULL OUTER JOIN**: All rows from both tables
5. **CROSS JOIN**: Cartesian product (every row × every row)

```sql
-- Inner join example
SELECT c.c_name, o.o_orderdate
FROM customer c
INNER JOIN orders o ON c.c_custkey = o.o_custkey;
```

### 6. GROUP BY & Aggregations
**Aggregate Functions:** `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`

```sql
-- Count orders by priority
SELECT o_orderpriority, COUNT(*) AS num_orders
FROM orders
GROUP BY o_orderpriority;

-- Average account balance by nation
SELECT c_nationkey, AVG(c_acctbal) AS avg_balance
FROM customer
GROUP BY c_nationkey;
```

**Key Insight:** GROUP BY combines multiple rows into summary rows - essential for analytics!

## 🔨 What I Built

### Project Setup
- Created project folder in `01_Projects/Data Engineering for Beginners/`
- Set up subfolders: Research/, Chats/, Daily Progress/
- Linked to code repository: `/Users/jonasblasques/Dev/Data_Engineering/data_engineering_for_beginners_code`

### SQL Exercises Completed
- Practiced SELECT statements with TPCH dataset
- Wrote queries with WHERE clause filtering
- Experimented with different JOIN types
- Created aggregation queries with GROUP BY

## 🤔 Questions & Challenges

- **Resolved:** Docker and Python environment set up successfully
- **New Question:** When to use LEFT vs RIGHT JOIN in practice? (seems like LEFT is more common)
- **Challenge:** Understanding when CROSS JOIN is actually useful in real scenarios
- **Note to self:** Practice more complex multi-table JOINs

## 📚 Resources & References

- [Chapter 1: SQL Basics](https://de101.startdataengineering.com/sql_basics) (sections 1.1-1.4.5)
- [Code Repository](file:///Users/jonasblasques/Dev/Data_Engineering/data_engineering_for_beginners_code)
- [[Research/SQL Basics - Quick Reference|SQL Quick Reference Guide]]
- TPCH Dataset: Bicycle parts seller data warehouse

## 🎯 Next Steps

1. [x] Complete Chapter 1 sections 1.1-1.4.5
2. [ ] Continue to section 1.5 and beyond
3. [ ] Complete remaining Chapter 1 sections
4. [ ] Work on Chapter 1 exercises
5. [ ] Move to Chapter 2: Advanced SQL

## 💭 Reflections

**What clicked:** The progression from basic SELECT to JOINs and GROUP BY makes sense. Seeing how these build on each other helps understand the "why" behind SQL's design.

**Practical insight:** Understanding JOIN types is critical for data engineering - most real-world queries involve combining data from multiple tables. The TPCH dataset (customer, orders, etc.) is a perfect example of normalized data that requires JOINs.

**Connection to data engineering:** This isn't just querying - it's about understanding how to transform and aggregate data at scale. Spark SQL will be key for processing large datasets in production pipelines.

---

**Links:** [[README|Project Overview]] | [[Research/]] | [[Chats/]]
