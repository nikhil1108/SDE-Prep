

## 📚 Core Concepts

### 1. Scalability
**Definition**: The ability of a system to handle increased load

#### Vertical Scaling (Scale Up)
- Add more power (CPU, RAM) to existing machine
- **Pros**: Simple, no code changes
- **Cons**: Hardware limits, single point of failure, expensive

#### Horizontal Scaling (Scale Out)
- Add more machines
- **Pros**: Better fault tolerance, easier to scale
- **Cons**: Complex, data inconsistency challenges

---

### 2. Load Balancing
**Purpose**: Distribute traffic across multiple servers

#### Algorithms
- **Round Robin**: Distribute requests sequentially
- **Least Connections**: Send to server with fewest active connections
- **IP Hash**: Route based on client IP
- **Weighted Round Robin**: Distribute based on server capacity

#### Types
- **Layer 4 (Transport)**: Based on IP and port
- **Layer 7 (Application)**: Based on HTTP headers, cookies, URL

**Popular Tools**: Nginx, HAProxy, AWS ELB

---

### 3. Caching
**Purpose**: Store frequently accessed data in fast storage

#### Caching Strategies
1. **Cache-Aside (Lazy Loading)**
   - App checks cache first
   - On miss, load from DB and update cache

2. **Write-Through**
   - Write to cache and DB simultaneously
   - Ensures consistency

3. **Write-Back (Write-Behind)**
   - Write to cache first
   - Async write to DB later
   - Fast writes, risk of data loss

4. **Refresh-Ahead**
   - Proactively refresh cache before expiry

#### Eviction Policies
- **LRU** (Least Recently Used)
- **LFU** (Least Frequently Used)
- **FIFO** (First In First Out)
- **Random Replacement**

**Popular Tools**: Redis, Memcached

---

### 4. Database Design

#### SQL (Relational)
**When to use**:
- Structured data
- ACID compliance needed
- Complex queries with joins
- Data integrity critical

**Examples**: PostgreSQL, MySQL, Oracle

#### NoSQL
**Types**:
1. **Document**: MongoDB, Couchbase
2. **Key-Value**: Redis, DynamoDB
3. **Column-Family**: Cassandra, HBase
4. **Graph**: Neo4j, Amazon Neptune

**When to use**:
- Unstructured/semi-structured data
- Horizontal scaling needed
- High write throughput
- Eventual consistency acceptable

---

### 5. Database Sharding
**Definition**: Partition data across multiple databases

#### Sharding Strategies
1. **Horizontal Sharding**: Split rows across shards
2. **Vertical Sharding**: Split columns (tables) across shards
3. **Hash-Based**: Hash key determines shard
4. **Range-Based**: Key ranges for each shard
5. **Directory-Based**: Lookup table for shard location

**Challenges**:
- Cross-shard queries
- Rebalancing
- Shard key selection

---

### 6. Database Replication
**Purpose**: Maintain copies of data for availability and performance

#### Types
1. **Master-Slave**
   - One master (writes), multiple slaves (reads)
   - Good for read-heavy workloads

2. **Master-Master**
   - Multiple masters accepting writes
   - Conflict resolution needed

3. **Synchronous**: Wait for replica acknowledgment
4. **Asynchronous**: Don't wait for replica

---

### 7. CAP Theorem
**Statement**: Distributed system can provide only 2 of 3:

- **C (Consistency)**: All nodes see same data at same time
- **A (Availability)**: Every request gets a response
- **P (Partition Tolerance)**: System works despite network partitions

**Examples**:
- **CP**: MongoDB, HBase, Redis (with clustering)
- **AP**: Cassandra, DynamoDB, Couchbase
- **CA**: Traditional RDBMS (but partition tolerance is necessary in distributed systems)

---

### 8. Consistency Patterns

#### Strong Consistency
- Read always returns latest write
- **Use**: Banking, financial transactions
- **Trade-off**: Higher latency, lower availability

#### Eventual Consistency
- Reads may return stale data temporarily
- **Use**: Social media feeds, DNS
- **Trade-off**: Better performance, potential inconsistency

#### Causal Consistency
- Causally related operations seen in order
- **Use**: Messaging systems

---

### 9. Message Queues
**Purpose**: Decouple components, async communication

#### Benefits
- **Decoupling**: Services independent
- **Scalability**: Handle traffic spikes
- **Reliability**: Message persistence
- **Async Processing**: Non-blocking operations

#### Popular Tools
- **Kafka**: High throughput, distributed log
- **RabbitMQ**: AMQP protocol, flexible routing
- **AWS SQS**: Managed, serverless
- **Redis Pub/Sub**: Fast, in-memory

**Patterns**:
- Point-to-Point (Queue)
- Publish-Subscribe (Topic)

---

### 10. Microservices Architecture

#### Characteristics
- Small, focused services
- Independently deployable
- Own database per service
- Communication via APIs

#### Pros
- Scalability
- Flexibility
- Fault isolation
- Technology diversity

#### Cons
- Complexity
- Network latency
- Data consistency challenges
- Debugging difficulty

---

### 11. API Design

#### REST (RESTful APIs)
- **Stateless**: Each request independent
- **HTTP Methods**: GET, POST, PUT, DELETE, PATCH
- **Resource-based**: URLs represent resources
- **Status Codes**: 200, 201, 400, 404, 500, etc.

#### GraphQL
- **Flexible**: Client specifies exact data needed
- **Single Endpoint**: One endpoint for all queries
- **Strongly Typed**: Schema definition

#### gRPC
- **High Performance**: Binary protocol (Protocol Buffers)
- **Bi-directional streaming**
- **Language agnostic**

---

### 12. CDN (Content Delivery Network)
**Purpose**: Deliver content from servers close to users

#### Benefits
- Lower latency
- Reduced load on origin servers
- Better availability
- DDoS protection

#### Use Cases
- Static assets (images, CSS, JS)
- Video streaming
- Software downloads

**Popular CDNs**: Cloudflare, Akamai, AWS CloudFront

---

### 13. Rate Limiting
**Purpose**: Control request rate to prevent abuse

#### Algorithms
1. **Token Bucket**: Tokens generated at fixed rate
2. **Leaky Bucket**: Requests processed at fixed rate
3. **Fixed Window Counter**: Count requests per time window
4. **Sliding Window Log**: Track timestamp of each request
5. **Sliding Window Counter**: Hybrid approach

---

### 14. Authentication & Authorization

#### Authentication (Who are you?)
- **Session-based**: Server stores session
- **Token-based**: JWT (JSON Web Token)
- **OAuth 2.0**: Third-party auth
- **SSO**: Single Sign-On

#### Authorization (What can you do?)
- **RBAC**: Role-Based Access Control
- **ABAC**: Attribute-Based Access Control
- **ACL**: Access Control Lists

---

### 15. Monitoring & Observability

#### Three Pillars
1. **Metrics**: Numerical measurements (CPU, memory, latency)
2. **Logs**: Event records
3. **Traces**: Request flow through system

#### Key Metrics
- **Latency**: Request response time
- **Throughput**: Requests per second
- **Error Rate**: Failed requests percentage
- **Saturation**: Resource utilization

**Tools**: Prometheus, Grafana, ELK Stack, Datadog, New Relic

---

### 16. Data Partitioning Strategies

1. **Horizontal Partitioning (Sharding)**: Divide rows
2. **Vertical Partitioning**: Divide columns
3. **Functional Partitioning**: By business function
4. **Hash Partitioning**: Hash function determines partition
5. **Range Partitioning**: Continuous ranges
6. **List Partitioning**: Discrete values

---

### 17. Consistent Hashing
**Purpose**: Distribute data evenly, minimize redistribution

#### Use Cases
- Load balancing
- Distributed caching
- Database sharding

#### Benefits
- Add/remove nodes with minimal data movement
- Uniform distribution
- Scalability

---

### 18. WebSockets
**Purpose**: Real-time, bi-directional communication

#### vs HTTP
- HTTP: Request-response, stateless
- WebSocket: Persistent connection, full-duplex

#### Use Cases
- Chat applications
- Real-time gaming
- Live sports scores
- Stock price updates

---

### 19. Database Indexing
**Purpose**: Speed up data retrieval

#### Types
- **B-Tree Index**: Most common, range queries
- **Hash Index**: Fast equality lookups
- **Bitmap Index**: Low-cardinality columns
- **Full-Text Index**: Text search

#### Trade-offs
- **Pros**: Faster reads
- **Cons**: Slower writes, storage overhead

---

### 20. Distributed Transactions
**Purpose**: ACID across multiple databases

#### Patterns
1. **2-Phase Commit (2PC)**
   - Prepare phase, commit phase
   - Blocking, coordinator single point of failure

2. **Saga Pattern**
   - Sequence of local transactions
   - Compensating transactions for rollback
   - Eventual consistency

3. **Event Sourcing**
   - Store events, not current state
   - Replay events to reconstruct state

---

## 📊 Quick Reference Table

| Concept | When to Use | Trade-offs |
|---------|-------------|------------|
| SQL | Structured data, ACID | Harder to scale horizontally |
| NoSQL | Unstructured, high scale | Eventual consistency |
| Caching | Frequent reads | Stale data, complexity |
| Sharding | Data too big for one DB | Cross-shard queries hard |
| Microservices | Large teams, complex app | Network overhead, complexity |
| Message Queue | Async processing, decoupling | Eventual consistency |
| CDN | Static content, global users | Stale content, cost |

---

## 🔗 Further Reading
- "Designing Data-Intensive Applications" by Martin Kleppmann
- System Design Primer (GitHub)
- AWS Well-Architected Framework
- Google SRE Book
