# Designing Data-Intensive Applications - Summary

**Author:** Martin Kleppmann
**Type:** Technical Reference
**Focus:** Distributed Systems, Data Architecture, System Design Principles

---

## Overview

"Designing Data-Intensive Applications" is a foundational text that explores the fundamental concepts, trade-offs, and engineering principles behind building modern data systems. Rather than a tool-specific tutorial, it provides deep insights into the "why" and "how" of data storage and processing, enabling informed architectural decisions.

---

## Core Philosophy: The RSM Triad

The book is built around three fundamental properties of data-intensive applications:

### Reliability
- System's ability to work correctly despite faults
- Types of faults: hardware, software, human error
- Design principle: **Embrace faults, don't assume their absence**

### Scalability
- System's ability to cope with increased load
- Considerations: data volume, traffic, complexity
- Measured by: latency, throughput, percentiles (not averages)

### Maintainability
- Ease of operation, understanding, and adaptation
- Three key aspects:
  - **Operability**: Easy to operate and monitor
  - **Simplicity**: Easy to understand (abstraction management)
  - **Evolvability**: Easy to adapt to changing requirements

---

## Part I: Foundations of Data Systems

### Data Models and Query Languages

**Three Primary Data Models:**

1. **Relational Model**
   - SQL-based
   - Strong for structured data and complex joins
   - Schema-on-write approach
   - Best for: ACID transactions, complex relationships

2. **Document Model (NoSQL)**
   - JSON/XML based
   - Flexible schemas (schema-on-read)
   - Good data locality for nested structures
   - Best for: semi-structured data, rapid iteration

3. **Graph Model**
   - Vertices, edges, properties
   - Query languages: Cypher, SPARQL, Datalog
   - Best for: highly interconnected data, complex relationships

**Key Insight:** No universal "best" model - choice depends on access patterns and data structure.

### Storage Engines

**Two Fundamental Approaches:**

1. **LSM-Trees (Log-Structured Merge-Trees)**
   - Append-only, sorted segments
   - Background merging and compaction
   - Advantages: High write throughput, efficient compression
   - Used by: Cassandra, HBase, LevelDB, RocksDB
   - Best for: Write-heavy workloads

2. **B-Trees**
   - Update-in-place, fixed-size pages
   - Standard for most relational databases
   - Advantages: Good random access, efficient range queries
   - Used by: PostgreSQL, MySQL, most RDBMS
   - Best for: Read-heavy workloads, transactional systems

**OLTP vs. OLAP:**
- **OLTP (Online Transaction Processing)**: Low-latency, many small reads/writes, row-oriented storage
- **OLAP (Online Analytical Processing)**: High-throughput, scanning large datasets, column-oriented storage

**Column-Oriented Storage:**
- Stores data by column rather than row
- Highly efficient for analytical queries
- Enables better compression and vectorized processing
- Used in: Parquet, ORC, most modern data warehouses

### Encoding and Evolution

**Data Encoding Formats:**
- **Language-specific**: Convenient but limited interoperability
- **Text-based**: JSON, XML - human-readable but verbose
- **Binary**: Thrift, Protocol Buffers, Avro - compact and efficient

**Schema Evolution:**
- **Forward compatibility**: Old code can read new data
- **Backward compatibility**: New code can read old data
- Critical for rolling upgrades and system evolution

---

## Part II: Distributed Data

### Replication Strategies

**1. Single-Leader Replication**
- One primary node handles all writes
- Followers replicate changes asynchronously or synchronously
- Simple but single point of failure
- Used by: Most RDBMS (PostgreSQL, MySQL)

**2. Multi-Leader Replication**
- Multiple nodes accept writes
- Asynchronous replication between leaders
- Challenges: Write conflicts requiring resolution
- Best for: Multi-datacenter setups, offline clients

**3. Leaderless Replication (Dynamo-style)**
- Clients write to multiple replicas in parallel
- Read from multiple replicas to resolve conflicts
- Employs quorums (W + R > N)
- Used by: Cassandra, DynamoDB, Riak

**Replication Lag Issues:**
- **Read-your-writes**: Ensure users see their own updates immediately
- **Monotonic reads**: Prevent reading older data after reading newer data
- **Consistent prefix reads**: Preserve causality of related writes

### Partitioning (Sharding)

**Two Main Approaches:**

1. **Key-Range Partitioning**
   - Split data by ranges of keys
   - Advantages: Efficient range queries
   - Disadvantages: Risk of hot spots

2. **Hash Partitioning**
   - Hash keys to distribute evenly
   - Advantages: Prevents hot spots
   - Disadvantages: Range queries require scatter-gather

**Secondary Index Partitioning:**
- **Document-partitioned (Local)**: Each partition maintains own indexes, requires scatter-gather for queries
- **Term-partitioned (Global)**: Indexes partitioned separately, single-partition reads but complex writes

### Transactions and Isolation Levels

**ACID Properties:**
- **Atomicity**: All-or-nothing execution
- **Consistency**: Application-specific invariants
- **Isolation**: Concurrent transactions don't interfere
- **Durability**: Committed writes survive failures

**Isolation Levels (weak to strong):**

1. **Read Committed**
   - No dirty reads, no dirty writes
   - Weakest practical level

2. **Snapshot Isolation (MVCC)**
   - Each transaction sees consistent snapshot
   - Prevents: Lost updates, read skew
   - Used by: Most modern databases

3. **Serializable**
   - Strongest isolation level
   - Appears as if transactions executed sequentially
   - Implementations:
     - **Two-Phase Locking (2PL)**: Pessimistic, can have deadlocks
     - **Serializable Snapshot Isolation (SSI)**: Optimistic, better performance
     - **Actual Serial Execution**: Literally one at a time

**Common Concurrency Anomalies:**
- Dirty reads/writes
- Lost updates
- Write skew
- Phantom reads

### The Trouble with Distributed Systems

**Fundamental Challenges:**

1. **Unreliable Networks**
   - Unbounded delays, packet loss
   - Network partitions (split-brain risk)
   - No way to distinguish slow from crashed nodes

2. **Unreliable Clocks**
   - Clock drift between machines
   - Time-of-day clocks can jump backward
   - Monotonic clocks only measure elapsed time

3. **Process Pauses**
   - Garbage collection pauses
   - VM suspensions
   - OS scheduling delays

**System Models:**
- **Synchronous**: Bounded delays (theoretical)
- **Partially synchronous**: Eventually timely (most real systems)
- **Asynchronous**: No timing guarantees

**Failure Models:**
- **Crash-stop**: Nodes fail by stopping
- **Crash-recovery**: Nodes can restart with stable storage
- **Byzantine**: Nodes can behave arbitrarily (malicious)

### Consistency and Consensus

**Consistency Models:**

1. **Eventual Consistency**
   - Given no new updates, all replicas eventually converge
   - Weakest guarantee, best availability

2. **Causal Consistency**
   - Preserves cause-and-effect relationships
   - Stronger than eventual, weaker than linearizability

3. **Linearizability**
   - Strongest consistency model
   - Appears as if single copy, operations atomic
   - Expensive in terms of performance and availability

**CAP Theorem Critique:**
- Oversimplified view of trade-offs
- Real question: What consistency guarantees during network partition?
- Most systems can be available and consistent when network is healthy

**Consensus Algorithms:**
- **Two-Phase Commit (2PC)**: Blocking protocol for atomic commits
- **Paxos**: Foundational consensus algorithm (complex)
- **Raft**: Easier-to-understand consensus (used in etcd)
- **Zab**: ZooKeeper Atomic Broadcast

**Use Cases:**
- Leader election
- Distributed locking
- Total order broadcast
- Atomic commit protocols

---

## Part III: Derived Data

### Batch Processing

**Core Principles:**
- Immutable input datasets
- Deterministic transformations
- Fault tolerance through task retries

**MapReduce Paradigm:**
- **Map**: Process each record independently
- **Shuffle**: Sort and partition by key
- **Reduce**: Aggregate records with same key

**Modern Batch Processing:**
- **Apache Spark**: In-memory processing, RDDs/DataFrames
- **Apache Flink**: Unified batch/stream processing
- **Dataflow Engines**: More flexible than MapReduce

**Advantages:**
- Strong fault tolerance
- Can process massive datasets
- Reproducible outputs

### Stream Processing

**Key Concepts:**

1. **Event Streams**
   - Unbounded data
   - Timestamped events
   - Append-only log

2. **Message Brokers vs. Log-Based Systems**
   - **Traditional Brokers**: RabbitMQ, ActiveMQ (delete after consumption)
   - **Log-Based**: Kafka, Kinesis (retain messages, replay capability)

3. **Time in Stream Processing**
   - **Event Time**: When event actually occurred
   - **Processing Time**: When system processes event
   - **Windows**: Tumbling, sliding, session windows

**Important Patterns:**

- **Change Data Capture (CDC)**: Stream database changes as events
- **Event Sourcing**: Store all state changes as immutable events
- **CQRS**: Separate read and write models

**Stream Joins:**
- Stream-stream joins
- Stream-table joins (enrichment)
- Table-table joins (materialized views)

### The Future of Data Systems

**Key Trends and Principles:**

1. **Unbundling Databases**
   - Separate storage from compute
   - Compose systems from specialized components

2. **Data Integration Through Derived Data**
   - Event logs as source of truth
   - Multiple specialized views derived from same events

3. **Dataflow Architecture**
   - Applications designed around data flow
   - Immutable events as communication mechanism

4. **End-to-End Correctness**
   - Don't trust lower-level guarantees alone
   - Implement application-level checks
   - Idempotency through unique operation IDs

5. **Ethical Considerations**
   - Data privacy and surveillance
   - Predictive analytics and bias
   - Transparency and accountability

---

## Key Design Principles

### 1. Embrace Trade-offs
No system can simultaneously optimize for all properties. Understand requirements and make informed compromises.

### 2. Design for Faults
Assume hardware will fail, software will have bugs, networks will be unreliable, and clocks will drift.

### 3. Measure Performance Properly
Use percentiles (p50, p95, p99) rather than averages, especially for user-facing systems.

### 4. Manage Complexity Through Abstraction
Hide implementation details behind well-defined interfaces. Strive for simplicity.

### 5. Separate Concerns
- OLTP vs. OLAP workloads
- Systems of record vs. derived data
- Storage vs. compute

### 6. Leverage Immutability and Event Logs
Treat data changes as append-only events. Simplifies debugging, recovery, and enables powerful patterns like CDC and Event Sourcing.

### 7. Understand Consistency Models
Don't blindly strive for strongest consistency. Choose weakest model that satisfies requirements.

### 8. Design for Evolution
Support schema evolution with backward and forward compatibility. Enable rolling upgrades.

### 9. Build End-to-End Correctness
Implement application-level checks, idempotency, and continuous auditing.

### 10. Consider the Human Element
Design for operability, provide good observability, and recognize ethical implications.

---

## Critical Takeaways for Data Engineers

1. **Master the fundamentals** - Tools change rapidly, but principles endure
2. **Think in trade-offs** - There are no silver bullets in distributed systems
3. **Data as events** - Viewing data changes as immutable event streams is powerful
4. **Consistency is nuanced** - Many levels exist; choose appropriately
5. **Design for failure** - Distributed systems will fail; design accordingly
6. **Storage engine matters** - LSM-Trees vs. B-Trees affects performance characteristics
7. **OLTP ≠ OLAP** - Different workloads require different architectures
8. **Replication and partitioning** - Essential for scale and availability
9. **End-to-end correctness** - Don't rely solely on infrastructure guarantees
10. **Be ethically aware** - Data systems have real-world consequences

---

## Related Concepts

- [[Data Engineering Lifecycle]]
- [[CAP Theorem]]
- [[Event-Driven Architecture]]
- [[Data Warehousing]]
- [[Stream Processing]]
- [[Apache Kafka]]

---

## References

- Book: "Designing Data-Intensive Applications" by Martin Kleppmann (O'Reilly, 2017)
- Related: System Design, Distributed Systems, Database Internals

---

*Created: 2025-10-18*
*Source: PDF analysis via Gemini Vision*
*Course: Data Engineering for Beginners*
