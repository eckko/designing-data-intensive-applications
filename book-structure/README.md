Version 2 (adds all 108 distinct book pictures, encrypted; plus 62 figure questions); version 1; kinds: system-design (chapters 1-11, with algorithms rungs in 3 and 9), architecture (chapter 12), expository (whole book). 834 ideas, 5053 questions, written by Sonnet 5.5.

# Designing Data-Intensive Applications: chapter map for review

Martin Kleppmann. Kleppmann explains the principles behind reliable, scalable and maintainable data systems: storage, replication, partitioning, transactions, distributed-systems trouble, and batch and stream processing.

Reviewed branch: `book-structure`. Nothing has been written yet; this is the plan.

## Units

| Unit | Title | Kind | Modifiers | Confidence | Pages | Weight | Ideas | Questions | HTRAB prefix |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Chapter 1 | Reliable, Scalable, and Maintainable Applications | system-design | none | medium | 26.2 | 1.0 | 31 | 184 | analytical/determining-an-authors-message |
| Chapter 2 | Data Models and Query Languages | system-design | has-code | medium | 42.9 | 1.0 | 50 | 301 | analytical/determining-an-authors-message |
| Chapter 3 | Storage and Retrieval | system-design (+algorithms) | none | medium | 45.1 | 1.1 | 58 | 349 | analytical/determining-an-authors-message |
| Chapter 4 | Encoding and Evolution | system-design | has-code | medium | 37.2 | 0.9 | 39 | 235 | analytical/determining-an-authors-message |
| Chapter 5 | Replication | system-design | none | high | 54.4 | 1.2 | 76 | 459 | analytical/determining-an-authors-message |
| Chapter 6 | Partitioning | system-design | none | high | 23.6 | 0.8 | 22 | 133 | analytical/determining-an-authors-message |
| Chapter 7 | Transactions | system-design | none | high | 59.4 | 1.3 | 90 | 542 | analytical/determining-an-authors-message |
| Chapter 8 | The Trouble with Distributed Systems | system-design | none | high | 57.1 | 1.2 | 80 | 481 | analytical/determining-an-authors-message |
| Chapter 9 | Consistency and Consensus | system-design (+algorithms) | none | high | 77.7 | 1.3 | 118 | 710 | analytical/determining-an-authors-message |
| Chapter 10 | Batch Processing | system-design | has-code | high | 62.8 | 1.1 | 81 | 485 | analytical/determining-an-authors-message |
| Chapter 11 | Stream Processing | system-design | none | high | 61.2 | 1.1 | 79 | 473 | analytical/determining-an-authors-message |
| Chapter 12 | The Future of Data Systems | architecture | none | medium | 85.5 | 1.2 | 120 | 721 | analytical/determining-an-authors-message |
| Whole book | Reading the book as a whole | expository | none | high | 8 | 1.0 | 9 | 56 | analytical/determining-an-authors-message |

### Chapter 1: Reliable, Scalable, and Maintainable Applications

Defines reliability, scalability and maintainability as the goals every data system is judged by, with the faults, load and change they must survive.

Kind reason: Goals and trade-offs of whole data systems: load, faults, scale.

Sub-headings: Thinking About Data Systems; Reliability; Hardware Faults; Software Errors; Human Errors; How Important Is Reliability?; Scalability; Describing Load; Describing Performance; Approaches for Coping with Load; Maintainability; Operability: Making Life Easy for Operations; Simplicity: Managing Complexity; Evolvability: Making Change Easy; Summary

### Chapter 2: Data Models and Query Languages

Compares relational, document and graph data models and the query languages that go with each, and what each makes easy or hard.

Kind reason: Model-choice trade-offs; SQL, JSON and query snippets appear but the point is the trade-off.

Sub-headings: Relational Model Versus Document Model; The Birth of NoSQL; The Object-Relational Mismatch; Many-to-One and Many-to-Many Relationships; Are Document Databases Repeating History?; Relational Versus Document Databases Today; Query Languages for Data; Declarative Queries on the Web; MapReduce Querying; Graph-Like Data Models; Property Graphs; The Cypher Query Language; Graph Queries in SQL; Triple-Stores and SPARQL; The Foundation: Datalog; Summary

### Chapter 3: Storage and Retrieval

Explains how databases store and index data: log-structured and B-tree engines, plus transaction versus analytics storage and column stores.

Kind reason: Engine internals with named structures (LSM, B-tree) judged by cost trade-offs; could be algorithms.

Sub-headings: Data Structures That Power Your Database; Hash Indexes; SSTables and LSM-Trees; B-Trees; Comparing B-Trees and LSM-Trees; Other Indexing Structures; Transaction Processing or Analytics?; Data Warehousing; Stars and Snowflakes: Schemas for Analytics; Column-Oriented Storage; Column Compression; Sort Order in Column Storage; Writing to Column-Oriented Storage; Aggregation: Data Cubes and Materialized Views; Summary

### Chapter 4: Encoding and Evolution

Compares encoding formats such as JSON, Thrift, Protocol Buffers and Avro, and how each handles schema change, compatibility and dataflow between processes.

Kind reason: Compatibility trade-offs between formats and dataflow modes; some schema snippets.

Sub-headings: Formats for Encoding Data; Language-Specific Formats; JSON, XML, and Binary Variants; Thrift and Protocol Buffers; Avro; The Merits of Schemas; Modes of Dataflow; Dataflow Through Databases; Dataflow Through Services: REST and RPC; Message-Passing Dataflow; Summary

### Chapter 5: Replication

Covers keeping copies of data on several machines: leader-follower, multi-leader and leaderless designs, replication lag, and conflict handling.

Kind reason: Replication, consistency and failure modes are the heart of system-design.

Sub-headings: Leaders and Followers; Synchronous Versus Asynchronous Replication; Setting Up New Followers; Handling Node Outages; Implementation of Replication Logs; Problems with Replication Lag; Reading Your Own Writes; Monotonic Reads; Consistent Prefix Reads; Solutions for Replication Lag; Multi-Leader Replication; Use Cases for Multi-Leader Replication; Handling Write Conflicts; Multi-Leader Replication Topologies; Leaderless Replication; Writing to the Database When a Node Is Down; Limitations of Quorum Consistency; Sloppy Quorums and Hinted Handoff; Detecting Concurrent Writes; Summary

### Chapter 6: Partitioning

Explains splitting data across nodes by key range or hash, secondary indexes, rebalancing and request routing.

Kind reason: Partitioning and routing trade-offs.

Sub-headings: Partitioning and Replication; Partitioning of Key-Value Data; Partitioning by Key Range; Partitioning by Hash of Key; Skewed Workloads and Relieving Hot Spots; Partitioning and Secondary Indexes; Partitioning Secondary Indexes by Document; Partitioning Secondary Indexes by Term; Rebalancing Partitions; Strategies for Rebalancing; Operations: Automatic or Manual Rebalancing; Request Routing; Parallel Query Execution; Summary

### Chapter 7: Transactions

Explains transactions, ACID, weak isolation levels and the anomalies they allow, and how serializability is achieved.

Kind reason: Consistency guarantees, anomalies and failure modes.

Sub-headings: The Slippery Concept of a Transaction; The Meaning of ACID; Single-Object and Multi-Object Operations; Weak Isolation Levels; Read Committed; Snapshot Isolation and Repeatable Read; Preventing Lost Updates; Write Skew and Phantoms; Serializability; Actual Serial Execution; Two-Phase Locking (2PL); Serializable Snapshot Isolation (SSI); Summary

### Chapter 8: The Trouble with Distributed Systems

Shows what goes wrong in distributed systems: unreliable networks, clocks and process pauses, and how to reason about truth and system models.

Kind reason: Failure modes of distributed systems.

Sub-headings: Faults and Partial Failures; Cloud Computing and Supercomputing; Unreliable Networks; Network Faults in Practice; Detecting Faults; Timeouts and Unbounded Delays; Synchronous Versus Asynchronous Networks; Unreliable Clocks; Monotonic Versus Time-of-Day Clocks; Clock Synchronization and Accuracy; Relying on Synchronized Clocks; Process Pauses; Knowledge, Truth, and Lies; The Truth Is Defined by the Majority; Byzantine Faults; System Model and Reality; Summary

### Chapter 9: Consistency and Consensus

Covers linearizability, ordering and causality, distributed transactions and consensus algorithms, and what each guarantee costs.

Kind reason: Consistency models and consensus trade-offs; some algorithm content (alsoKind algorithms).

Sub-headings: Consistency Guarantees; Linearizability; What Makes a System Linearizable?; Relying on Linearizability; Implementing Linearizable Systems; The Cost of Linearizability; Ordering Guarantees; Ordering and Causality; Sequence Number Ordering; Total Order Broadcast; Distributed Transactions and Consensus; Atomic Commit and Two-Phase Commit (2PC); Distributed Transactions in Practice; Fault-Tolerant Consensus; Membership and Coordination Services; Summary

### Chapter 10: Batch Processing

Explains batch processing from Unix tools to MapReduce and dataflow engines, joins and grouping, and how outputs are built from immutable inputs.

Kind reason: Processing models and their trade-offs.

Sub-headings: Batch Processing with Unix Tools; Simple Log Analysis; The Unix Philosophy; MapReduce and Distributed Filesystems; MapReduce Job Execution; Reduce-Side Joins and Grouping; Map-Side Joins; The Output of Batch Workflows; Comparing Hadoop to Distributed Databases; Beyond MapReduce; Materialization of Intermediate State; Graphs and Iterative Processing; High-Level APIs and Languages; Summary

### Chapter 11: Stream Processing

Covers event streams, message brokers and logs, databases as streams, stream joins, time reasoning and fault tolerance.

Kind reason: Messaging, ordering and failure handling.

Sub-headings: Transmitting Event Streams; Messaging Systems; Partitioned Logs; Databases and Streams; Keeping Systems in Sync; Change Data Capture; Event Sourcing; State, Streams, and Immutability; Processing Streams; Uses of Stream Processing; Reasoning About Time; Stream Joins; Fault Tolerance; Summary

### Chapter 12: The Future of Data Systems

Argues for integrating specialised systems through derived data and dataflow, designing for correctness and auditability, and doing right by the people whose data it is.

Kind reason: Architecture of combined systems (dataflow, derived data) plus an ethics section in prose.

Sub-headings: Data Integration; Combining Specialized Tools by Deriving Data; Batch and Stream Processing; Unbundling Databases; Composing Data Storage Technologies; Designing Applications Around Dataflow; Observing Derived State; Aiming for Correctness; The End-to-End Argument for Databases; Enforcing Constraints; Timeliness and Integrity; Trust, but Verify; Doing the Right Thing; Predictive Analytics; Privacy and Tracking; Summary

### Whole book: Reading the book as a whole

Puts the book together: how reliability, scale, models, replication, transactions and derived data combine, and which design to reach for in a given situation.

Kind reason: Final whole-book unit is always expository.

Sub-headings: Whole book

## Excluded
Cover, copyright, contents, glossary, index, about the author, colophon; the Preface (it only outlines the book); each chapter's reference list.

## Grouping
One unit per chapter (12 chapters of 7,000 to 26,000 words each); no grouping needed. Part headings (I, II, III) are not units. Pages are estimated (words / 300) from the chapter text with each reference list removed.

## Plan
- Writer model: Sonnet 5.5. Questions per page: 8.
- Total: about 641.1 pages, 5129 questions, roughly 853 ideas.
- Cost is high for a book this size. It can be done in rounds (a few chapters at a time) or at a lower density (for example 4 per page).

## Will not cover
Diagrams and figures (text-only until media is added), the Preface, the Glossary, the Index and the reference lists. Chapter 9 and Chapter 3 borrow extra rungs from the algorithms kind.

## How to review
Answer yes or no in the chat. Changes are pushed to this same branch.
