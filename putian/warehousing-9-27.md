# Data Warehousing Knowledge Points and Colab Project Plan

This guide combines the key ideas from the data warehousing lecture files with a practical Google Colab project sequence aligned to the Fall 2026 DSSA 5102 schedule. The Python and Colab introduction is completed in Weeks 1–2, so the sequence below begins with Week 3 and develops one cumulative workplace-oriented warehouse project.

## Course Project Scenario

Students build an **operations data warehouse** from public service-request data. The same design can represent help-desk tickets, maintenance work orders, incidents, claims, orders, inspections, or other workplace cases.

The project follows this data flow:

```text
Public files and APIs
        ↓
Raw reproducible data
        ↓
Cleaned and validated tables
        ↓
SQLite operational database
        ↓
Star-schema analytical warehouse
        ↓
Batch reports and reliability checks
```

The initial dataset can use these fields:

```text
request_id
created_at
updated_at
borough
agency
complaint_type
status
priority
estimated_cost
customer_id
```

Related inputs can include `agencies.csv`, `locations.csv`, and an append-only `request_events.jsonl` file. Synthetic data should be used when real records contain confidential, sensitive, or personally identifiable information.

## Fall 2026 Weekly Colab Sequence

| Week | Scheduled focus | Practical Colab demonstration | Main warehousing concepts | Student artifact |
|---|---|---|---|---|
| 3 | Data structures for manipulation | Represent one service request as a dictionary, flat row, normalized tables, nested JSON document, and event list | Relational and document models, schema-on-read, data locality | Data-representation comparison |
| 4 | Public open-source dataset processing | Acquire, profile, clean, preserve, and document a public dataset | ETL, provenance, source-of-record thinking, data quality | Raw and cleaned datasets with verification |
| 5 | Data mining techniques | Analyze workload trends, resolution times, backlogs, unusual records, and missingness | OLAP, dimensions, measures, aggregates, responsible analysis | Exploratory analysis and proposed warehouse measures |
| 6 | APIs and other interfaces | Retrieve paginated API data with timeouts, retries, caching, validation, and restart support | Network uncertainty, encoding, compatibility, idempotence | Reproducible API ingestion function |
| 7 | Advanced SQL, pandas, and NumPy | Load clean data into SQLite and answer equivalent questions with SQL and pandas | Relational modeling, joins, declarative queries | SQLite operational database |
| 8 | Advanced SQL, pandas, and NumPy | Integrate related tables, reconcile unmatched keys, and implement reusable transformations | Data integration, data contracts, query planning | Validated integrated analytical dataset |
| 9 | Storage, retrieval, indexes, and lookup | Benchmark SQLite queries before and after indexing; compare CSV and Parquet | Index tradeoffs, row and column storage, lookup performance | Storage and query benchmark report |
| 10 | Mini warehouse design | Create fact and dimension tables and load a star schema | OLTP and OLAP, grain, facts, dimensions, surrogate keys | Mini analytical warehouse |
| 11 | Batch-style notebook processing | Process daily files in chunks and incrementally load only new data | Batch processing, partitions, checkpoints, replay, idempotence | Restart-safe batch pipeline |
| 12 | Thanksgiving break | No new demonstration | — | — |
| 13 | Reliability and integration concepts | Inject duplicates, late events, schema changes, partial failures, and stale derived data | Transactions, retries, CDC, consistency, auditability | Reliability and integration test |
| 14 | Group project demonstration | Demonstrate the source-to-report pipeline and its verification evidence | Full lifecycle integration | Final project demonstration |
| 15 | Backup and wrap-up | Conduct a recovery test, peer review, or project correction | Maintainability, limitations, reflection | Corrected final package |

## Demonstration Specifications

### Week 3 Data Representations

Students represent the same record in several forms and evaluate them against practical questions.

```python
request = {
    "request_id": "R1001",
    "created_at": "2026-09-22T09:15:00",
    "agency": "Public Works",
    "category": "Street Repair",
    "location": {"borough": "North", "zip_code": "08201"},
    "status": "OPEN",
}
```

They compare the difficulty of retrieving a complete request, counting requests by agency, updating shared location information, preserving status history, and representing many-to-many relationships.

### Week 4 Reproducible Public-Data Intake

The notebook creates separate raw, clean, and report outputs. Students record the source URL, steward, retrieval date, license or terms, and limitations. The raw source remains unchanged. The cleaned file is saved, reloaded, and verified.

```python
assert cleaned["request_id"].notna().all()
assert cleaned["request_id"].is_unique
assert cleaned["created_at"].notna().mean() > 0.95
assert set(cleaned["status"]).issubset({"OPEN", "IN_PROGRESS", "CLOSED"})
```

### Week 5 Operational Data Mining

Students investigate request volume, median and p95 resolution time, seasonal patterns, backlog, expensive or long-running cases, duplicate categories, and missing-data patterns. The findings are translated into candidate dimensions and measures instead of remaining disconnected charts.

```text
Candidate dimensions: date, location, agency, request category, priority
Candidate measures: request count, resolution hours, estimated cost, SLA violation
```

Students must distinguish observed associations from causal conclusions and identify how incomplete or biased source data affects the analysis.

### Week 6 Reliable API Ingestion

The API workflow handles pagination, rate limits, timeouts, empty responses, duplicate pages, schema changes, and interrupted downloads. Each completed page is saved before the next request. A rerun continues from the last verified page rather than starting again or duplicating records.

The exercise demonstrates that a network call differs from a local function call: a timeout does not prove whether the remote operation failed, succeeded, or produced a response that was lost.

### Weeks 7 and 8 Operational SQL and Integration

SQLite provides a Colab-friendly operational database with tables such as:

```text
requests
request_events
agencies
locations
categories
source_files
```

Students practice keys, joins, grouped summaries, common table expressions, window functions, duplicate detection, and reconciliation. They compare equivalent SQL and pandas transformations and report unmatched references instead of silently discarding them.

```sql
SELECT r.request_id
FROM requests AS r
LEFT JOIN agencies AS a
    ON r.agency_id = a.agency_id
WHERE a.agency_id IS NULL;
```

### Week 9 Storage and Indexing Benchmark

Students use enough synthetic records to make performance differences visible. They inspect a query plan and time a selective query before and after creating a relevant index.

```sql
CREATE INDEX idx_requests_agency_status
ON requests(agency_id, status);
```

The benchmark records query time, insert time, query plan, database size, and the workload being tested. Students also compare CSV and Parquet file size, full-read time, selected-column read time, and type preservation. Conclusions must remain workload-specific.

### Week 10 Mini Warehouse

Students define the grain as **one row per service request** and build this star schema:

```text
                    dim_date
                       |
dim_location — fact_request — dim_category
                       |
                   dim_agency
                       |
                 dim_priority
```

The fact table can contain request identifiers, dimension keys, resolution hours, estimated cost, and an SLA-violation indicator. Students load dimensions before facts, generate surrogate keys, handle unknown members explicitly, and verify foreign-key coverage.

```python
assert len(fact_request) == cleaned["request_id"].nunique()
assert fact_request["request_key"].is_unique
assert fact_request["agency_key"].notna().all()
```

A useful extension is a Type 2 slowly changing dimension. For example, when a location changes region, the dimension retains `valid_from`, `valid_to`, and `is_current` so historical facts join to the correct version.

### Week 11 Restart-Safe Batch Processing

Students process several daily or monthly source files. The notebook computes a checksum, checks a `processed_files` table, reads unprocessed inputs in chunks, validates each chunk, loads it in a transaction, and records successful completion.

The instructor deliberately raises an exception halfway through one file. Students verify that the transaction prevents a partial load and that rerunning the notebook neither loses nor duplicates records.

### Week 13 Warehouse Failure Lab

The final technical demonstration deliberately introduces:

- Duplicate event delivery, corrected with a unique `event_id` and idempotent upsert.
- A partial multi-table update, corrected with a transaction and rollback.
- A new, missing, renamed, or incorrectly typed field, handled through explicit schema validation.
- A late closure event, handled by recalculating the affected aggregate and recording the correction.
- An operational update not yet reflected in the warehouse, used to measure and discuss acceptable lag.
- Unnecessary customer details, used to decide which fields to exclude, mask, aggregate, or delete.

Replication, quorums, conflict resolution, logical clocks, and consensus should be illustrated with small Python simulations rather than real clusters. Real Kafka, Hadoop, Spark, ZooKeeper, or Raft deployments add infrastructure that is not required to understand the underlying behavior in a Colab course.

## Standard Notebook Pattern

Every demonstration should follow the same reproducible evidence loop:

1. State the workplace problem.
2. Identify the relevant knowledge points.
3. Describe the data model or architecture.
4. Create or load a small reproducible dataset.
5. Run a baseline implementation.
6. Introduce a realistic failure or limitation.
7. Implement an improved approach.
8. Print assertions, counts, timings, or reconciliation evidence.
9. Interpret the result for workplace use.
10. Document limitations, provenance, privacy, and responsible use.
11. Save and reload the resulting artifact.

## Colab Technical Stack

- `pandas` for cleaning, transformations, profiling, and verification.
- `sqlite3` for relational modeling, SQL, indexes, constraints, and transactions.
- DuckDB for analytical SQL and direct Parquet queries when installation is available.
- PyArrow and Parquet for column-oriented storage.
- Matplotlib or Seaborn for operational and performance charts.
- Standard Python collections, generators, and functions for event, replica, retry, partition, and failure simulations.

No exercise should require Linux shell commands, Docker, paid cloud services, private credentials, GPUs, or a persistent distributed cluster.

## Final Group Project Requirements

The final project should include:

- At least two source files, tables, or formats.
- Source provenance and an unchanged raw-data layer.
- Cleaning, typing, validation, and reconciliation evidence.
- An operational or integrated SQLite layer.
- A documented star schema with a clearly stated fact-table grain.
- One slowly changing dimension or another justified history strategy.
- An incremental, idempotent, or restart-safe load.
- One index or storage-format benchmark.
- Analytical results that include a useful operational measure such as median and p95 resolution time.
- A deliberate failure-and-recovery demonstration.
- A data dictionary and architecture diagram.
- Privacy, retention, ethics, and limitations discussions.
- A notebook that runs from top to bottom and saves reloadable outputs.

The Week 14 presentation should demonstrate the pipeline and verification evidence, not only charts. A complete submission may include the Colab notebook, sample inputs, cleaned CSV or Parquet outputs, SQLite warehouse, data dictionary, architecture diagram, verification report, and presentation.

## Concept Reference from the Original Warehousing Lectures

The following units preserve the detailed concepts from the original lecture files. Their original week numbers are retained only in the source filenames; the units below are reference topics and do not represent the Fall 2026 calendar.

## Concept Unit 1 — Reliable, Scalable, and Maintainable Applications

- Data-intensive applications commonly combine databases, caches, search indexes, stream processing, and batch processing.
- The three central nonfunctional qualities are reliability, scalability, and maintainability.
- A **fault** is one component deviating from its specification; a **failure** is the system as a whole no longer providing its required service.
- Fault-tolerant systems anticipate faults and continue operating. At scale, systems should tolerate the loss of entire machines and support rolling upgrades.
- Reliability threats include hardware faults, correlated software errors, and human/configuration errors.
- Reliability improves through safe interfaces, sandbox environments, automated testing, gradual deployment, rollback and recomputation tools, telemetry, training, and sound operational practices.
- Scalability must be discussed in terms of explicit load parameters, such as requests per second, read/write ratios, data volume, record size, or active users.
- The Twitter timeline example illustrates the choice between **fan-out on read** and **fan-out on write**, as well as a hybrid approach for users with exceptionally large followings.
- Batch systems are often measured by **throughput**; online systems are commonly measured by response time.
- **Latency** is time waiting to be handled, whereas **response time** is the total time observed by the client.
- Medians and tail percentiles such as p95, p99, and p99.9 reveal performance better than a simple average. Tail latency matters especially when one user request makes many parallel backend calls.
- SLOs define performance and availability targets; SLAs turn such expectations into customer-facing commitments.
- Scaling up adds capacity to one machine; scaling out distributes work across machines; elastic systems adjust resources automatically.
- Scalable architecture depends on the particular workload rather than data throughput alone.
- Maintainability includes **operability** (easy to run), **simplicity** (low accidental complexity), and **evolvability** (easy to change).
- Abstraction reduces accidental complexity by hiding implementation details behind understandable interfaces.
- Functional requirements describe what a system does; nonfunctional requirements describe qualities such as reliability, security, scalability, compliance, and maintainability.

## Concept Unit 2 — Data Models and Query Languages

- Applications layer data models so that each layer hides lower-level complexity behind an abstraction.
- Relational databases remain strong for transaction and batch processing, joins, and many-to-one or many-to-many relationships.
- NoSQL adoption has been driven by scalability, open-source availability, specialized query patterns, and demand for more flexible models.
- **Object-relational impedance mismatch** is the gap between application objects and relational tables; ORMs reduce boilerplate but do not eliminate the underlying differences.
- Document databases reduce impedance mismatch and offer locality by keeping related data together, especially for one-to-many tree structures.
- Document-model advantages include schema flexibility, locality, and similarity to application structures; disadvantages include weak joins and complexity for highly connected data.
- The hierarchical model gives each record one parent; the network model permits multiple parents but requires navigating fixed access paths.
- The relational model separates logical queries from physical access paths, allowing a query optimizer to choose joins, indexes, and execution order.
- Choose a document model for naturally self-contained documents; prefer relational or graph models when relationships dominate.
- **Schema-on-read** accepts heterogeneous records and interprets structure when data is read; **schema-on-write** validates structure before storage.
- Data locality speeds whole-document reads but may waste I/O for partial reads and make large-document updates expensive.
- Relational and document systems are converging through features such as JSON columns and improved join/reference support.
- Declarative query languages specify the desired result, leaving the execution strategy to the system. This enables optimization and parallelization.
- MapReduce separates mapping and reduction into pure functions, but declarative aggregation pipelines are usually easier to optimize and use.
- Graph models are natural when many-to-many relationships dominate. Graphs contain vertices and edges and support algorithms such as shortest paths and ranking.
- A property graph stores properties on vertices and edges; triple stores represent subject–predicate–object statements.
- Cypher, SPARQL, and Datalog are declarative approaches to querying graph-shaped data.

## Concept Unit 3 — Storage and Retrieval

- A database storage engine must persist data and retrieve it efficiently while handling concurrency, crashes, and disk-space reclamation.
- An append-only **log** simplifies writes; an **index** is an additional structure derived from primary data to accelerate reads.
- Every index improves selected reads but adds storage and write overhead, so indexes should reflect actual query patterns.
- A hash index maps keys to byte offsets in log files. It works well when all keys fit in memory and range queries are unnecessary.
- Segmenting, compacting, and merging append-only logs discard overwritten values and control disk usage.
- Tombstones represent deletions; checksums detect corruption; snapshots speed index recovery; immutable segments simplify concurrent reads.
- **SSTables** keep each segment sorted by key, enabling merge-sort compaction, sparse in-memory indexes, range scans, and block compression.
- An **LSM-tree** accepts writes into an in-memory memtable, records them in a recovery log, flushes sorted SSTables, and compacts them in the background.
- Size-tiered and leveled compaction trade disk usage, write cost, and read behavior differently.
- **B-trees** organize sorted keys into fixed-size pages and update data in place, splitting pages as needed.
- LSM-trees generally favor write throughput and compression; B-trees commonly favor predictable reads and strong range-lock-based transactional behavior.
- LSM compaction can consume substantial I/O and create latency spikes; B-trees can suffer fragmentation and write amplification.
- Secondary indexes map non-primary attributes to one or more matching row identifiers.
- Full-text and fuzzy search require specialized indexes that can handle terms, variants, proximity, and misspellings.
- In-memory databases serve reads from RAM but still need logs, snapshots, special hardware, or replication for durability.
- **OLTP** handles many small, low-latency transactions; **OLAP** scans large numbers of records and selected columns to compute aggregates.
- A data warehouse separates analytical queries from operational workloads and receives cleaned, transformed copies of operational data through ETL or continuous updates.
- In a **star schema**, a large fact table records events or measurements while dimension tables describe who, what, where, when, how, and why.
- Column-oriented storage reads only required columns, compresses repetitive values effectively, and supports vectorized processing.
- Column stores are excellent for analytical scans but make random writes and in-place updates more difficult.
- Materialized views precompute denormalized results; an OLAP cube is a materialized grid of aggregates across dimensions. Faster reads come at the cost of update work.

## Concept Unit 4 — Encoding and Evolution

- Systems must often support old and new code and data formats simultaneously during rolling upgrades.
- **Backward compatibility** means new code can read old data; **forward compatibility** means old code can read new data.
- Encoding or serialization converts in-memory structures into bytes; decoding or deserialization reconstructs in-memory structures.
- Language-native serialization is often unsuitable for long-lived interchange because of language coupling, security risks, weak versioning, and inefficiency.
- JSON, XML, and CSV are readable and widespread but have limitations involving number precision, binary data, schema enforcement, and size.
- Thrift and Protocol Buffers use schemas, field tags, and compact binary representations.
- Stable field tags let old readers ignore unknown fields. New fields should be optional or have defaults, removed tags must not be reused, and type changes can cause truncation.
- Avro decodes data by resolving differences between the writer's schema and reader's schema.
- In Avro, added or removed fields need defaults for compatibility; compatible type conversions are possible, while renaming fields is more difficult.
- Schema identifiers can be stored once per file, once per record, or negotiated when a network connection is established.
- Avro works well for dynamically generated schemas and database exports because it uses field names rather than manually assigned field tags.
- Schema-based binary formats are compact, self-documenting, compatibility-checkable, and capable of generating typed code.
- **Data outlives code**: databases may contain records written years earlier, so compatibility is a persistent requirement.
- Database dataflow pairs writers as encoders with readers as decoders. Schema migrations can be expensive and may be avoided for simple compatible changes.
- Network calls differ fundamentally from local function calls: requests can be delayed, lost, timed out, retried, or executed more than once.
- REST is easy to inspect and widely used for public APIs; RPC is common for internal service communication but should expose network uncertainty rather than hide it.
- Asynchronous brokers buffer messages, redeliver after failures, decouple endpoint locations, and support multiple consumers.
- Queues and topics connect producers to consumers; common brokers include RabbitMQ, ActiveMQ, NATS, and Kafka.
- Actor models isolate mutable state inside actors and communicate through asynchronous messages; distributed actors still require compatible encodings for rolling upgrades.

## Concept Unit 5 — Replication and Partitioning

- Replication keeps copies of data on multiple machines to reduce geographic latency, increase availability, and scale read throughput.
- In leader-based replication, all writes go through one leader and followers apply its replication log; reads may be served by the leader or followers.
- Synchronous replication improves durability and freshness but can block writes; asynchronous replication improves availability and latency but risks lag or data loss during failover.
- A new follower starts from a consistent snapshot and then replays changes made after that snapshot.
- Follower recovery replays missed log entries; leader failover requires detecting failure, electing/promoting a new leader, rerouting clients, and preventing split brain.
- Replication logs may use statement-based, write-ahead-log, logical row-based, or trigger-based techniques.
- Replication lag can violate read-after-write, monotonic-read, and consistent-prefix expectations.
- **Read-your-writes** ensures users see their own updates; **monotonic reads** prevent later reads from moving backward in time; **consistent-prefix reads** preserve causal ordering.
- Multi-leader replication supports multi-datacenter operation, offline clients, and collaborative editing but introduces write conflicts.
- Conflict handling can avoid conflicts through routing, resolve them during write or read, merge values, retain multiple versions, or choose a winner. Last-write-wins is simple but can lose data.
- Replication topology may be circular, star-shaped, or all-to-all; topology affects fault tolerance, loops, and event ordering.
- Leaderless systems send reads and writes to multiple replicas and repair stale copies through read repair or anti-entropy.
- With `n` replicas, `w` successful writes, and `r` read responses, `w + r > n` creates overlapping quorums under normal assumptions, but does not eliminate all stale-read or concurrency anomalies.
- Sloppy quorums write temporarily to reachable non-home nodes; hinted handoff later returns those writes to the intended replicas.
- Concurrent operations lack a happens-before relationship. Version vectors track per-replica versions and distinguish overwrites from concurrent writes.
- CRDTs aim to merge concurrent changes automatically without losing information.
- Partitioning or sharding divides a large dataset so storage and query load can be distributed across nodes; replication provides copies of each partition for fault tolerance.
- Key-range partitioning supports efficient range scans but can create hot spots; hash partitioning spreads load more evenly but scatters ranges.
- Random prefixes or suffixes can distribute a hot key's writes, at the cost of combining multiple keys during reads.
- Local secondary indexes require scatter/gather queries; global term-partitioned indexes improve reads but make writes and consistency harder.
- Rebalancing strategies include fixed partitions, dynamic splitting, and partitions proportional to nodes. `hash(key) mod N` is poor because changing `N` moves most keys.
- Fully automatic rebalancing can overload a cluster; operational oversight can reduce surprises.
- Request routing may be handled by any node, a routing tier, or partition-aware clients. Coordination services or gossip disseminate partition assignments.
- MPP databases decompose complex analytical queries into stages and partitions that execute in parallel.

## Concept Unit 6 — Transactions

- A transaction groups multiple operations into one logical unit so they commit together or abort together.
- **Atomicity** provides all-or-nothing execution; **consistency** preserves application-defined invariants; **isolation** makes concurrent transactions behave safely; **durability** preserves committed data after faults.
- Safe retries are central to abort handling, but retries may duplicate an operation if the commit succeeded and only the acknowledgement was lost.
- Retry logic should consider exponential backoff, overload, external side effects, deduplication, and client failure.
- Read committed prevents dirty reads and dirty writes, commonly through row-level write locks and retention of the previous committed value.
- Read committed still permits read skew or non-repeatable reads.
- Snapshot isolation gives a transaction a consistent database snapshot and is commonly implemented with multi-version concurrency control (MVCC).
- A **lost update** occurs when concurrent read-modify-write cycles overwrite one another.
- Lost updates can be prevented with database-side atomic operations, explicit locks such as `SELECT ... FOR UPDATE`, automatic conflict detection, or compare-and-set.
- Replicated systems may preserve conflicting versions and merge them later rather than relying on a single lock.
- **Write skew** occurs when transactions read the same condition but update different rows, jointly violating an invariant. Snapshot isolation alone may not prevent it.
- **Phantoms** occur when one transaction inserts or changes rows that alter another transaction's predicate result.
- Serializable isolation guarantees an outcome equivalent to some serial execution and prevents the full set of transaction race conditions.
- Actual serial execution is simple but limited by one core unless data is partitioned; cross-partition transactions remain expensive.
- Two-phase locking (2PL) uses shared and exclusive locks held until transaction end. It is unrelated to two-phase commit (2PC).
- 2PL prevents many anomalies but can produce deadlocks, blocking, unstable latency, and reduced throughput.
- Predicate locks cover all records matching a condition, including future records; index-range locks are a more practical approximation.
- Serializable snapshot isolation (SSI) is optimistic: it allows transactions to proceed, detects dangerous serialization conflicts, and aborts transactions when necessary.
- SSI performs well under low contention but depends on manageable abort rates and relatively short read-write transactions.

## Concept Unit 7 — Distributed Systems

- Distributed systems experience partial failures: some components may be broken while others continue working, and failure behavior is nondeterministic.
- A shared-nothing system communicates over an unreliable asynchronous network in which requests or responses can be lost, delayed, or queued.
- A timeout cannot reveal whether a request was lost, the remote node failed, the response was lost, or the remote operation actually succeeded.
- Short timeouts detect failure quickly but create false positives; long timeouts delay recovery. Timeouts should be informed by measured round-trip-time distributions and jitter.
- False failure detection may duplicate work and overload surviving nodes during responsibility transfer.
- Queueing can occur in switches, operating systems, virtual machines, TCP flow control, and busy application processes.
- Packet networks use capacity efficiently for bursty traffic but do not provide bounded delay like a dedicated circuit.
- Each machine has its own clock. NTP reduces but does not eliminate clock error.
- Time-of-day clocks may jump and are unsafe for measuring elapsed time; monotonic clocks move forward and are appropriate for local durations and timeouts.
- Physical timestamps are dangerous for ordering distributed events and can cause last-write-wins data loss.
- Logical clocks capture relative ordering without claiming to measure wall-clock or elapsed time.
- Clock readings have uncertainty intervals. Google Spanner uses tightly controlled clock uncertainty and commit waiting to order transactions across datacenters.
- Process pauses may result from garbage collection, scheduling, virtualization, paging, disk I/O, suspension, or signals, so a node cannot assume uninterrupted execution.
- Leases expire with time, but a paused former leader may resume and act after its authority has ended.
- A **fencing token** is a monotonically increasing number attached to each granted lease; storage rejects writes carrying an older token.
- Nodes should not trust their own failure judgments. Quorums let a majority establish shared knowledge.
- Byzantine faults involve nodes behaving arbitrarily or dishonestly; Byzantine fault tolerance is needed only in environments that include such threat assumptions.

## Concept Unit 8 — Consistency and Consensus

- Eventual consistency guarantees convergence only after writes stop and enough unspecified time passes.
- Stronger guarantees simplify application reasoning but may cost latency, availability, or throughput.
- **Linearizability** makes a replicated system appear to contain one atomic copy: once a write completes, subsequent reads must observe it.
- Serializability concerns the valid ordering of transactions; linearizability adds real-time recency for operations on individual objects.
- Distributed locks, leader election, and hard uniqueness constraints require linearizable coordination.
- Single-leader or consensus-backed systems can be linearizable; asynchronous multi-leader systems are not, and leaderless systems generally require special mechanisms.
- During a network partition, a linearizable system must reject operations from replicas that cannot coordinate with the authoritative side.
- CAP specifically concerns the choice between linearizability and availability during network partitions; it is not a general “pick any two” design rule.
- Causality is a partial order: causally related events are ordered while concurrent events may be incomparable.
- Causal consistency is stronger than eventual consistency and can remain available without waiting for distant nodes.
- Sequence numbers from one leader reflect log order. Independent per-node counters or wall clocks do not automatically preserve cross-node causality.
- A Lamport timestamp combines a logical counter and node ID to produce a total order consistent with causality.
- Total-order broadcast provides reliable delivery and the same delivery order to every node; it can be viewed as a replicated append-only log.
- State-machine replication applies identical ordered operations to every replica.
- Total-order broadcast can support linearizable writes; linearizable reads require additional synchronization with the log or a synchronously updated replica.
- Two-phase commit (2PC) coordinates an atomic outcome across participants using prepare/vote and commit-or-abort phases.
- After voting yes, participants may block if the coordinator fails; the coordinator must persist its decision and retry delivery after recovery.
- 2PC is not a consensus algorithm and differs from 2PL. XA standardizes 2PC across heterogeneous systems but adds latency, blocking, and operational complexity.
- Consensus requires uniform agreement, integrity, validity, and termination. Paxos, Raft, Zab, and Viewstamped Replication are major consensus families.
- Consensus protocols elect a unique leader within an epoch/term and use overlapping quorums for elections and proposals.
- Consensus normally requires a majority, can suffer from false failure detection and repeated elections, and has costs similar to synchronous replication.
- ZooKeeper and etcd use consensus to provide linearizable operations, ordered updates, leases, watches, leader election, service discovery, and membership coordination.
- Coordination services hold small, slow-changing metadata—not the main application dataset.

## Concept Unit 9 — Batch and Stream Processing

- Online services answer requests, batch systems process finite datasets offline, and stream systems process unbounded event flows continuously or near real time.
- Unix pipelines demonstrate composability through a common byte-stream interface, immutable input, visible intermediate behavior, and small single-purpose programs.
- MapReduce applies mapper and reducer functions to data in a distributed filesystem such as HDFS.
- HDFS uses shared-nothing storage, a NameNode for block locations, and replicated or erasure-coded blocks for fault tolerance.
- MapReduce partitions work, places computation near input data, groups all values for the same key, and performs a distributed sort-and-merge called the **shuffle**.
- MapReduce workflows materialize each job's output to files. This is robust but adds disk, replication, and scheduling overhead.
- Joins in MapReduce often require full scans. Map-side, skewed, and shared joins can improve performance under suitable assumptions.
- Hot keys create reducer skew and must be detected, replicated, or divided among reducers.
- Batch jobs should avoid per-record network writes to external databases. Building immutable output files and bulk-loading them is faster, safer, and easier to retry.
- MPP databases optimize analytical SQL and favor memory; MapReduce accepts arbitrary formats/programs, materializes to disk, and tolerates individual task failures.
- Spark, Tez, and Flink treat a workflow as a dataflow graph and avoid unnecessary HDFS materialization.
- Spark recomputes lost partitions using RDD lineage; Flink restores operators from checkpoints.
- Iterative graph processing uses bulk synchronous parallel/Pregel-style supersteps, stateful vertices, message passing, and periodic checkpoints.
- Stream processing operates on **events** produced by publishers and consumed by subscribers, usually grouped into topics or streams.
- When producers outrun consumers, a system may drop events, buffer them, or apply backpressure.
- Direct delivery offers low latency but weak offline/failure handling; message brokers centralize buffering, durability, subscriptions, and acknowledgements.
- Queue load balancing sends each message to one consumer; fan-out sends each message to every subscribed consumer.
- Redelivery prevents loss but may reorder or duplicate messages, so consumers must tolerate repeated processing.
- Log-based brokers such as Kafka retain an append-only, partitioned history. Each partition has ordered offsets, and consumers control and persist their own positions.
- Partitioned logs provide replay and scalable throughput, but consumer parallelism is bounded by the number of partitions and ordering is only guaranteed within a partition.
- Consumer lag should be monitored; retention must be long enough for slow consumers or they will miss deleted segments.
- Dual writes to a database plus cache, index, or warehouse can race or partially fail and leave systems inconsistent.
- **Change data capture (CDC)** exposes database changes as an event stream so downstream search indexes, caches, and warehouses can behave as derived data systems.
- A consistent snapshot plus a known log offset allows a new CDC consumer to bootstrap and then apply incremental changes.
- Log compaction retains the latest value per key and uses tombstones for deletions.
- **Event sourcing** stores domain-level immutable events as the source of truth and reconstructs current state or new views by replaying them.
- Commands may be rejected; accepted events are durable facts and should not be rejected by consumers.
- CQRS separates the write model from read-optimized derived views.
- Immutable event histories improve auditability, debugging, recovery, and view evolution, but complicate deletion, privacy requirements, and high-churn workloads.
- Stream processors may create materialized views, notifications, derived streams, complex-event detections, or real-time analytics.
- Event time describes when something happened; processing time describes when the system handled it. Confusing them produces incorrect windows when events are delayed.
- Late events require an explicit policy: drop and measure them, or revise/retract prior window results.
- Tumbling windows do not overlap; hopping windows overlap at a fixed step; sliding windows follow event proximity; session windows end after inactivity.
- Stream-stream joins retain recent events from both streams; stream-table joins enrich events using changing reference data; table-table joins maintain derived relationships.
- Time-dependent joins must use the historically correct dimension version to remain deterministic; this is the slowly changing dimension problem.
- Exactly-once or effectively-once semantics means the visible result is as if each input were processed once, even if work was retried.
- Micro-batching and checkpoints enable recovery, but external side effects still need atomicity, deduplication, or idempotence.
- Idempotent operations have the same effect when repeated. Unique operation IDs and end-to-end deduplication are practical correctness tools.
- Stateful stream processors recover through snapshots, replicated changelogs, or redundant processing.
- Logs order change; deterministic and idempotent consumers propagate that change to loosely coupled derived systems.
- Batch processing reprocesses large historical datasets; stream processing updates views with low latency. Together they support correction and evolution.
- Lambda architecture combines a fast stream-produced view with a slower exact batch-produced view, though operating two implementations adds complexity.
- Federated databases unify reads across storage systems; unbundled databases use logs to unify writes across specialized systems.
- Asynchronous dataflow improves fault isolation and team independence, but it generally sacrifices immediate read-your-writes behavior.
- Correctness must be considered end to end. A client-generated request ID should flow through every component to prevent duplicate effects after retries.
- **Timeliness** means users see current state; **integrity** means data is not corrupted, lost, contradictory, or falsely derived. Asynchronous systems may weaken timeliness while preserving integrity.
- Strict uniqueness requires coordination or a single ordered partition; some business constraints can instead be temporarily violated and repaired later.
- Auditing, restore testing, self-validation, append-only histories, and Merkle-tree-based verification help establish that data remains correct.
- Data systems have ethical responsibilities: biased input can amplify unfairness, automated decisions need accountability and appeal, and systems should be evaluated in their full social context.
- Privacy means individual control over disclosure, not merely secrecy. Meaningful consent, data minimization, limited retention, transparency, and protection against surveillance are core design concerns.

## Cross-Cutting Design Principles

- Make workload assumptions explicit before choosing an architecture.
- Treat failure, retries, concurrency, version changes, and partial outages as normal operating conditions.
- Prefer immutable logs and deterministic recomputation when they simplify recovery and auditing.
- Choose consistency and coordination guarantees according to application invariants, not by default.
- Separate systems of record from derived views, and define how updates, lag, replay, and reconciliation work.
- Optimize storage layout for the dominant workload: row-oriented for transactional access, column-oriented for analytical scans, and logs for sequential change propagation.
- Make operations idempotent and carry stable request identifiers end to end.
- Measure tail latency, replication/consumer lag, abort and retry rates, clock health, and rebalancing/compaction pressure.
- Design for schema evolution because data usually survives longer than application code.
- Include security, privacy, fairness, auditability, human dignity, and deletion requirements in system design from the beginning.

## Source Lectures

- `wk_02_reliable_scalable_maintainable_apps.md`
- `wk_03_data_models_and_query_languages.md`
- `wk_04_storage_and_retrieval.md`
- `wk_05_encoding_and_evolution.md`
- `wk_06_replication_and_partitioning.md`
- `wk_07_transactions.md`
- `wk_08_distributed_systems.md`
- `wk_09_consistency_and_concensus.md`
- `wk_10_batch_and_stream_processing.md`

## Course Schedule Reference

- `DSSA-5102-Fall-2026.docx`
