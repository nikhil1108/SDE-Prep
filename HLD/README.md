

## 🎯 Overview
High Level Design focuses on the architecture of large-scale distributed systems, covering scalability, reliability, availability, and performance.

## 🏗️ System Design Problems

### 1. URL Shortener (TinyURL)
**Difficulty**: Medium  
**Key Concepts**: Hashing, Database Design, Caching

**Requirements**:
- Generate short URL from long URL
- Redirect short URL to original
- Handle billions of URLs
- Analytics tracking

**Topics to Cover**:
- Base62 encoding
- Database schema (SQL vs NoSQL)
- Caching strategy (Redis)
- Rate limiting
- Analytics

---

### 2. Rate Limiter
**Difficulty**: Medium  
**Key Concepts**: Distributed Systems, Algorithms

**Algorithms**:
- Token Bucket
- Leaky Bucket
- Fixed Window Counter
- Sliding Window Log
- Sliding Window Counter

**Requirements**:
- Per-user rate limiting
- Per-API rate limiting
- Distributed rate limiting
- Different rate limit rules

---

### 3. Distributed Cache
**Difficulty**: Medium-Hard  
**Key Concepts**: Caching, Distributed Systems

**Requirements**:
- Get/Put operations
- Eviction policies (LRU, LFU)
- Distributed caching
- Cache invalidation
- Consistency

**Topics**:
- Consistent hashing
- Replication
- Data partitioning

---

### 4. WhatsApp/Chat System
**Difficulty**: Hard  
**Key Concepts**: WebSockets, Message Queues, Databases

**Requirements**:
- One-to-one messaging
- Group messaging
- Message delivery status
- Online/Offline status
- Media sharing
- End-to-end encryption

**Components**:
- WebSocket servers
- Message queue (Kafka)
- Database (Cassandra)
- CDN for media
- Notification service

---

### 5. Uber/Ride Sharing
**Difficulty**: Hard  
**Key Concepts**: Geospatial Indexing, Real-time Systems

**Requirements**:
- Real-time location tracking
- Driver-rider matching
- ETA calculation
- Pricing (surge pricing)
- Trip management

**Topics**:
- QuadTree/Geohash
- Google S2 library
- WebSocket for real-time updates
- Payment integration

---

### 6. Video Streaming (YouTube/Netflix)
**Difficulty**: Hard  
**Key Concepts**: CDN, Video Processing, Recommendations

**Requirements**:
- Video upload and processing
- Video streaming
- Recommendations
- Search functionality
- Comments and likes

**Components**:
- Video transcoding pipeline
- CDN architecture
- Adaptive bitrate streaming
- ML-based recommendations

---

### 7. Social Media (Twitter/Instagram)
**Difficulty**: Hard  
**Key Concepts**: Feed Generation, Scalability

**Requirements**:
- User posts/tweets
- News feed generation
- Follow/Unfollow
- Likes, comments, shares
- Trending topics
- Search

**Topics**:
- Fan-out on write vs read
- Feed ranking algorithms
- Timeline generation
- Graph database for relationships

---

### 8. Search Engine (Google)
**Difficulty**: Very Hard  
**Key Concepts**: Crawling, Indexing, Ranking

**Components**:
- Web crawler
- Inverted index
- PageRank algorithm
- Query processing
- Distributed storage

---

### 9. File Storage (Dropbox/Google Drive)
**Difficulty**: Hard  
**Key Concepts**: Chunking, Sync, Storage

**Requirements**:
- File upload/download
- File sync across devices
- Sharing and permissions
- Version control
- Deduplication

**Topics**:
- Chunking algorithm
- Metadata database
- Block storage
- Sync protocol

---

### 10. Notification Service
**Difficulty**: Medium  
**Key Concepts**: Message Queue, Push Notifications

**Requirements**:
- Multiple channels (email, SMS, push)
- Priority handling
- Template management
- Rate limiting
- Analytics

**Components**:
- Message queue (Kafka/RabbitMQ)
- Worker services
- Third-party integrations (Twilio, SendGrid)

## 📋 System Design Checklist

### Step 1: Requirements Clarification (5 min)
- [ ] Functional requirements
- [ ] Non-functional requirements (scalability, availability, consistency)
- [ ] Constraints (latency, throughput)
- [ ] Scale (users, requests, data size)

### Step 2: Capacity Estimation (5 min)
- [ ] Traffic estimates
- [ ] Storage estimates
- [ ] Bandwidth estimates
- [ ] Memory/Cache estimates

### Step 3: High-Level Design (10-15 min)
- [ ] Draw main components
- [ ] Define APIs
- [ ] Database schema
- [ ] Core workflows

### Step 4: Deep Dive (15-20 min)
- [ ] Scalability
- [ ] Database partitioning/sharding
- [ ] Caching strategy
- [ ] Load balancing
- [ ] Replication
- [ ] Monitoring and alerting

### Step 5: Trade-offs & Bottlenecks (5 min)
- [ ] Identify bottlenecks
- [ ] Discuss trade-offs
- [ ] Alternative approaches

## 🔑 Key Concepts to Master

### Scalability
- Horizontal vs Vertical scaling
- Stateless vs Stateful services
- Database scaling (read replicas, sharding)

### Performance
- Caching (Redis, Memcached)
- CDN
- Load balancing
- Database indexing

### Reliability & Availability
- Replication
- Fault tolerance
- Redundancy
- Health checks

### Consistency
- CAP theorem
- Eventual consistency
- Strong consistency
- ACID vs BASE

### Communication
- REST vs GraphQL
- gRPC
- WebSockets
- Message queues (Kafka, RabbitMQ)

### Data Storage
- SQL vs NoSQL
- When to use: PostgreSQL, MySQL, MongoDB, Cassandra, Redis
- Data partitioning strategies

### Monitoring
- Logging
- Metrics
- Distributed tracing
- Alerting

## 📊 Numbers Everyone Should Know

```
L1 cache reference:           0.5 ns
L2 cache reference:           7 ns
RAM reference:                100 ns
Read 1 MB sequentially (SSD): 1,000 µs = 1 ms
Disk seek:                    10 ms
Read 1 MB sequentially (HDD): 20 ms
Send packet CA->NL->CA:       150 ms
```

## 📝 Template for HLD Problems

```
## [System Name]

### 1. Requirements
**Functional:**
- Requirement 1
- Requirement 2

**Non-Functional:**
- Scalability
- Availability
- Latency
- Consistency

### 2. Capacity Estimation
- Users: X million
- Requests/day: Y billion
- Storage: Z TB
- Bandwidth: A Gbps

### 3. API Design
- API 1: `POST /api/v1/...`
- API 2: `GET /api/v1/...`

### 4. Database Schema
[Tables and relationships]

### 5. High-Level Architecture
[Diagram/Description]

### 6. Detailed Design
**Component 1:**
- Description
- Technology choices

**Component 2:**
- Description
- Technology choices

### 7. Scalability & Bottlenecks
- Bottleneck 1: Solution
- Bottleneck 2: Solution

### 8. Trade-offs
- Decision 1: Pros/Cons
- Decision 2: Pros/Cons
```

## 🔗 Resources
- Designing Data-Intensive Applications (Book)
- System Design Primer (GitHub)
- Grokking the System Design Interview
- ByteByteGo YouTube Channel
