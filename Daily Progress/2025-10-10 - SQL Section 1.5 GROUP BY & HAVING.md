# 2025-10-10 - SQL Basics Chapter 1 Complete! 🎉

**Module:** Module 1 - SQL Data Transformation
**Time Spent:** Full session
**Status:** ✅ Chapter 1 Complete (Sections 1.1-1.12)

---

## 📝 Today's Goals

- [x] Complete section 1.5 - GROUP BY deep dive
- [x] Complete section 1.5.1 - HAVING clause
- [x] Complete sections 1.6-1.11 (CASE, UNION, Subqueries, CAST/COALESCE, Functions, Views)
- [x] Complete Chapter 1 exercises (1.12)

## 💡 What I Learned

### Section 1.5: Combine Data from Multiple Rows using GROUP BY

**Core Concept:** Most analytical queries require calculating metrics by combining data from multiple rows. GROUP BY is the foundation of data aggregation.

**How GROUP BY Works:**
- Groups rows by specified column(s)
- Applies aggregate functions to each group
- Returns one row per group

**Example Use Case:** Create a report showing number of orders per priority segment

```sql
SELECT
  o_orderpriority,
  COUNT(*) AS num_orders
FROM
  orders
GROUP BY
  o_orderpriority;
```

**Key Insight:** Data is grouped by `orderpriority`, then `COUNT(*)` is calculated for each group separately.

### Aggregate Functions Available:
- `SUM` - Total of values
- `MIN` - Minimum value
- `MAX` - Maximum value
- `AVG` - Average of values
- `COUNT` - Count of rows

---

### Section 1.5.1: Use HAVING to Filter Based on Aggregates

**Problem:** What if you want to filter based on the aggregated results?
- `WHERE` filters rows **before** aggregation
- `HAVING` filters groups **after** aggregation

**Syntax Rule:** `HAVING` must come **after** the `GROUP BY` clause

```sql
SELECT
  o_orderpriority,
  COUNT(*) AS num_orders
FROM
  orders
GROUP BY
  o_orderpriority
HAVING
  COUNT(*) > 3;
```

**What this does:**
1. Groups orders by priority
2. Counts orders in each group
3. Only returns groups with more than 3 orders

**Critical Distinction:**
```sql
-- WHERE filters individual rows BEFORE grouping
WHERE o_totalprice > 1000

-- HAVING filters groups AFTER aggregation
HAVING COUNT(*) > 3
```

---

### Section 1.6: Replicate IF.ELSE Logic with CASE Statements

**Core Concept:** Use CASE statements for conditional logic within SQL queries.

```sql
SELECT
    o_orderkey,
    o_totalprice,
    CASE
        WHEN o_totalprice > 100000 THEN 'high'
        WHEN o_totalprice BETWEEN 25000 AND 100000 THEN 'medium'
        ELSE 'low'
    END AS order_price_bucket
FROM orders;
```

**Use Cases:**
- Creating categorical/bucketed data
- Complex conditional transformations
- Multiple conditions with WHEN clauses
- Default handling with ELSE

---

### Section 1.7: Stack Tables with UNION and EXCEPT

**UNION:** Combines results from multiple queries (removes duplicates)
**UNION ALL:** Combines results (keeps duplicates)
**EXCEPT:** Subtracts one query result from another

```sql
-- UNION (removes duplicates)
SELECT c_custkey, c_name FROM customer WHERE c_name LIKE '%_91%'
UNION
SELECT c_custkey, c_name FROM customer WHERE c_name LIKE '%_92%';

-- EXCEPT (subtract results)
SELECT c_custkey, c_name FROM customer WHERE c_name LIKE '%_91%'
EXCEPT
SELECT c_custkey, c_name FROM customer WHERE c_name LIKE '%191%';
```

**Key Insight:** UNION/EXCEPT require both queries to have the same number of columns and compatible data types.

---

### Section 1.8: Subqueries

**Core Concept:** Use a query result as a table in another query (nested queries).

```sql
SELECT
  n.n_name AS nation_name,
  s.quantity AS supplied_items
FROM nation n
LEFT JOIN (
    SELECT n.n_nationkey, SUM(l_quantity) AS quantity
    FROM lineitem l
    JOIN supplier s ON l.l_suppkey = s.s_suppkey
    JOIN nation n ON s.s_nationkey = n.n_nationkey
    GROUP BY n.n_nationkey
) s ON n.n_nationkey = s.n_nationkey;
```

**Use Cases:**
- Complex aggregations before joining
- Multi-step transformations
- Breaking down complex logic into manageable parts

---

### Section 1.9: Change Data Types (CAST) and Handle NULLs (COALESCE)

**CAST:** Convert data from one type to another
**COALESCE:** Return the first non-null value from a list

```sql
-- CAST example
SELECT CAST(o_orderdate AS STRING) FROM orders;

-- COALESCE example (handle nulls)
SELECT COALESCE(phone_number, 'No phone') FROM customer;
```

**Key Insight:** Essential for data quality - handle nulls gracefully and ensure correct data types.

---

### Section 1.10: Use Standard Built-in Database Functions

**Categories:**
- **String functions:** CONCAT, UPPER, LOWER, LENGTH, SUBSTRING
- **Date/Time functions:** CURRENT_DATE, DATE_ADD, DATE_DIFF, YEAR, MONTH
- **Numeric functions:** ROUND, FLOOR, CEIL, ABS

**Practical Use:** Data cleaning, transformation, and formatting in queries.

---

### Section 1.11: Save Queries as Views

**Core Concept:** Create reusable virtual tables from queries.

```sql
CREATE VIEW high_value_orders AS
SELECT *
FROM orders
WHERE o_totalprice > 100000;

-- Use the view like a table
SELECT * FROM high_value_orders;
```

**Benefits:**
- Simplify complex queries
- Reusable logic
- Abstract complexity for other users
- Security (limit access to certain columns)

---

### Section 1.12: Exercises

Completed 5 SQL challenge problems applying all concepts learned.

---

## 🔨 What I Built

- **GROUP BY queries** with multiple aggregations
- **CASE statements** for data bucketing
- **UNION/EXCEPT** queries for set operations
- **Subqueries** for complex multi-step transformations
- **Views** for reusable query logic
- **Complete exercises** demonstrating mastery of SQL fundamentals

---

## 🤔 Questions & Challenges

**Resolved:**
- ✅ WHERE vs HAVING: WHERE filters before grouping, HAVING after
- ✅ Can use both in same query (WHERE first, then HAVING)
- ✅ All non-aggregated SELECT columns must be in GROUP BY

**New Insights:**
- CASE statements are incredibly powerful for data transformation
- Subqueries help break complex logic into readable steps
- Views are essential for reusable analytics patterns
- COALESCE is critical for production queries (handle nulls!)

---

## 📚 Resources & References

- [Chapter 1: SQL Basics - Complete](https://de101.startdataengineering.com/sql_basics)
- [[Research/SQL Basics - Quick Reference|SQL Quick Reference Guide]]
- Previous: [[2025-10-09 - SQL Basics (Chapter 1)|Yesterday's Progress - Sections 1.1-1.4.5]]

---

## 🎯 Next Steps

1. [x] Complete all Chapter 1 sections (1.1-1.12)
2. [x] Complete Chapter 1 exercises
3. [ ] Review and consolidate SQL knowledge
4. [ ] Move to Chapter 2: Advanced SQL patterns
5. [ ] Apply SQL knowledge to real data engineering problems

---

## 💭 Reflections

**Massive Progress Today!** 🚀

Completed the entire SQL Basics chapter in one session. The progression from basic SELECT statements to advanced concepts like subqueries and views shows how SQL builds on itself naturally.

**Key Takeaways:**
- **Foundation is solid:** SELECT, WHERE, JOINs, GROUP BY form the core
- **Advanced tools are essential:** CASE, subqueries, and views make complex analytics possible
- **Data quality matters:** COALESCE and CAST are critical for production code
- **Think in sets:** SQL is declarative - focus on *what* you want, not *how* to get it

**Real-World Connection:**
These aren't just academic exercises. Every concept maps directly to data engineering:
- GROUP BY → analytics and aggregations
- Subqueries → ETL transformations
- Views → data marts and abstraction layers
- CASE → data categorization and bucketing

**Ready for the next level:** Chapter 2 will build on these fundamentals with more advanced patterns. The foundation is rock solid.

---

**Links:** [[README|Project Overview]] | [[Research/]] | [[Chats/]]
