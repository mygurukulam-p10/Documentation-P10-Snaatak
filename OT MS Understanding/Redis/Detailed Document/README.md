# Redis Documentation

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 06-09-24    | Version 1  | Komal Jaiswal   | 06-09-24       |

## Table of Contents

1. [What is a Database and Cache?](#1-what-is-a-database-and-cache)
2. [Why We Are Learning Redis and the Problems It Addresses](#2-why-we-are-learning-redis-and-the-problems-it-addresses)
3. [Alternatives and Comparison](#3-alternatives-and-comparison)
4. [Key Features of Redis](#4-key-features-of-redis)
5. [Block Architecture of Redis](#5-block-architecture-of-redis)
6. [Types of Redis Architecture](#6-types-of-redis-architecture)
7. [Services Redis Provides](#7-services-redis-provides)
8. [Best Practices for Tuning and Security](#8-best-practices-for-tuning-and-security)
9. [Observability](#9-observability)
10. [Use Cases of Redis](#10-use-cases-of-redis)
11. [Advantages and Disadvantages](#advantages-and-disadvantages)
12. [Conclusion](#conclusion)
13. [References](#references)

## 1. What is a Database and Cache?

### Database
- Persistent storage system for structured data.
- Supports CRUD operations (Create, Read, Update, Delete).
- Ensures data integrity and consistency.
- **Examples:** MySQL, PostgreSQL, MongoDB.

### Cache
- Temporary storage layer for frequently accessed data.
- Improves application performance by reducing database load.
- Typically stores data in memory for faster access.
- **Examples:** Redis, Memcached.

## 2. Why We Are Learning Redis and the Problems It Addresses

1. **Performance Bottleneck:**
   - Provides in-memory data storage for high-speed data access.
   - Reduces latency in data retrieval operations.

2. **Data Caching:**
   - Efficiently caches frequently accessed data.
   - Reduces load on primary databases.

3. **Session Management:**
   - Stores and manages user session data.
   - Enables quick retrieval of session information.

4. **Real-time Analytics:**
   - Supports real-time data processing and analysis.
   - Provides data structures suitable for analytics use cases.

5. **Scalability Challenges:**
   - Offers clustering and replication for horizontal scaling.
   - Supports high throughput and low latency at scale.

6. **Message Queuing:**
   - Implements Pub/Sub messaging system.
   - Facilitates communication between different parts of an application.

7. **Data Persistence and Reliability:**
   - Offers options for data persistence (RDB and AOF).
   - Supports replication for high availability.

## 3. Alternatives and Comparison

### Redis vs Memcached
- Both are in-memory key-value stores.
- Redis supports more complex data structures.
- Redis offers persistence and replication.

### Redis vs MongoDB
- MongoDB is a document-oriented database.
- Redis is primarily an in-memory data store.
- MongoDB is better for complex queries, Redis for fast read/write operations.

### Redis vs PostgreSQL
- PostgreSQL is a relational database.
- Redis is faster for simple operations.
- PostgreSQL offers more advanced querying capabilities.
- **Purpose with Redis:** Use Redis for caching and rapid data access, while PostgreSQL handles complex transactions and structured data storage.

### Redis vs MySQL
- MySQL is a relational database.
- Redis provides faster read/write for simpler data structures.
- MySQL offers ACID compliance for complex transactions.

### Redis vs ScyllaDB
- ScyllaDB is a distributed NoSQL database.
- Redis offers simpler setup and management.
- ScyllaDB provides better scalability for large datasets.
- **Purpose with Redis:** Leverage Redis for caching and real-time data access, while ScyllaDB handles large-scale, distributed data with low-latency access.

## 4. Key Features of Redis

- **Data Structures Supported:** Strings, hashes, lists, sets, sorted sets, bitmaps, hyperloglogs, geospatial indexes, and streams.
- **Pub/Sub Messaging:** Enables message communication between different parts of an application.
- **Transactions:** Supports atomic operations using MULTI, EXEC, and DISCARD commands.
- **Lua Scripting:** Allows execution of custom scripts.
- **Replication:** Master-slave replication for high availability.
- **Persistence:** Options for snapshots and append-only file persistence.
- **Cluster Mode:** Supports horizontal scaling and sharding.

## 5. Block Architecture of Redis

The Redis architecture can be divided into three main components: the Client, the Server, and the Storage. Let's examine each in detail:

### 1. Redis Client

- The Redis Client is the interface through which applications interact with Redis.
- Examples of Redis clients include:
  - `jedis`: A popular Java client for Redis
  - `ioredis`: A robust, performance-focused Redis client for Node.js

- Clients send commands to the Redis server and receive responses.
- They handle connection management, command pipelining, and response parsing.

### 2. Redis Server

The Redis Server is the core of the Redis architecture and consists of several components:

#### 2.1 Redis Engine

- The Redis Engine is the central processing unit of Redis.
- It handles:
  - Command execution
  - Data structure management
  - Event loop for non-blocking I/O operations

#### 2.2 Keyspace

- The Keyspace is where Redis stores all its key-value pairs.
- It's an in-memory dictionary that maps keys to their corresponding values.
- The Keyspace is central to Redis's fast read and write operations.

#### 2.3 Commands

- This component represents the set of Redis commands available for data manipulation and management.
- It includes operations for various data structures like strings, lists, sets, hashes, etc.
- Examples: `GET`, `SET`, `LPUSH`, `HSET`, `ZADD`, etc.

#### 2.4 RAM

- Redis primarily operates in-memory, using RAM for data storage.
- This is key to Redis's high-performance characteristics.
- The image shows binary data (011101010111...) to represent data stored in RAM.

#### 2.5 Device (CPU/GPU/TPU)

- This represents the hardware resources used by Redis.
- While Redis primarily uses CPU, some operations can be optimized for GPU or TPU in specialized setups.

### 3. Storage

- Although Redis is primarily an in-memory database, it offers persistence options:
  - **AOF (Append-Only File):** Logs every write operation received by the server.
  - **RDB (Redis Database):** Creates point-in-time snapshots of the dataset.
- The Storage component represents the disk where these persistence files are stored.

### Data Flow

1. The Redis Client sends commands to the Server.
2. The Redis Engine processes these commands, interacting with the Keyspace and executing the appropriate operations.
3. Data is read from or written to RAM.
4. If persistence is enabled, data changes are written to Storage using AOF or RDB methods.

This architecture allows Redis to provide high-speed data access while also offering options for data durability and persistence.

![Redis Architecture Original](https://github.com/user-attachments/assets/3ad7c849-87c6-4d05-8031-20b331454a82)

## 6. Types of Redis Architecture

1. **Standalone:**
   - Single Redis instance.
   - Suitable for small-scale applications.

![image](https://github.com/user-attachments/assets/a1e27646-e040-4168-bbc1-202df9b64701)

2. **Sentinel:**
   - Provides high availability.
   - Monitors Redis instances and performs automatic failover.

![image](https://github.com/user-attachments/assets/bfebb03d-6215-44c6-b46f-45816eb05a6c)

3. **Cluster:**
   - Horizontal scaling through sharding.
   - Distributes data across multiple nodes.

![image](https://github.com/user-attachments/assets/95988c21-4932-4b0d-8d77-d45dd8c7abe7)

## 7. Services Redis Provides

### Free
- Open-source Redis.
- Basic monitoring and management tools.

### Enterprise
- Redis Enterprise Cloud.
- Advanced security features.
- Enhanced scalability and performance.
- Professional support and SLAs.

## 8. Best Practices for Tuning and Security

### Tuning and Security Best Practices

| **Category**        | **Practice**                                        | **Description**                                                                 |
|---------------------|-----------------------------------------------------|---------------------------------------------------------------------------------|
| **Tuning**          | TCP-KeepAlive                                       | Enable to maintain connections.                                                 |
|                     | Pipelining                                          | Use to reduce network round trips.                                              |
|                     | Max-Connection                                      | Set appropriate limits on connections.                                          |
|                     | Overcommit Memory                                   | Configure for optimal memory usage.                                             |
|                     | RDB Persistence and Append Only File                | Balance between performance and durability.                                     |
|                     | Transparent Huge Page (THP)                         | Disable for better performance.                                                 |
| **Security**        | Access Control                                      | Implement strong authentication mechanisms.                                     |
|                     | Encryption                                          | Use SSL/TLS for securing data in transit.                                       |
|                     | Regular Security Updates                            | Keep Redis and the operating system updated regularly.                         |
|                     | Network Binding                                     | Bind Redis to specific network interfaces to limit exposure.                    |
|                     | Firewall Rules                                      | Restrict access to Redis ports using firewall rules.                            |
|                     | Authentication                                      | Use strong passwords or ACLs (Access Control Lists).                           |
|                     | Disable Dangerous Commands                          | Limit or disable potentially harmful operations.                               |
|                     | Protected Mode                                      | Enable for additional security in default configurations.                      |
|                     | Monitoring and Alerting                             | Set up systems to detect and respond to suspicious activities.                 |

## 9. Observability

### Metrics
- Memory Utilization.
- CPU Usage.
- Connection Metrics.
- Keyspace Metrics.
- Expired/Evicted Keys.
- Latency.
- Persistence Statistics.

### Dashboards
- **Grafana:** For visualizing Redis metrics.
- **Prometheus:** For collecting and storing metrics.

### Alerting
- Set up alerts for critical metrics and thresholds.

## 10. Use Cases of Redis

1. Caching layer for databases.
2. Session management in web applications.
3. Real-time analytics and leaderboards.
4. Message queues and pub/sub systems.
5. Job management in distributed systems.
6. Geospatial data storage and querying.
7. Rate limiting and throttling.

## Advantages and Disadvantages

| Advantages | Disadvantages |
|------------|---------------|
| High performance due to in-memory storage | Limited by available RAM |
| Versatile data structures | Potential data loss in case of crashes (if not configured for persistence) |
| Built-in replication and high availability | Complex cluster setup for large-scale deployments |
| Supports pub/sub messaging | Limited querying capabilities compared to traditional databases |
| Persistence options (RDB and AOF) | Requires careful memory management |
| Active community and ecosystem | Learning curve for optimal usage |
| Scalable through clustering | Potential consistency issues in distributed setups |
| Low latency for read/write operations | Not suitable for complex transactions or joins |
| Built-in Lua scripting | Limited built-in security features in open-source version |
| Atomic operations on data structures | Requires additional tools for comprehensive monitoring |

## Conclusion

Redis is a powerful in-memory data structure store that serves as a database, cache, and message broker. It is known for its high performance, versatility in supporting various data structures, and its ability to handle complex use cases like real-time analytics, session management, and message queuing. While it comes with certain limitations, such as memory constraints and a need for careful setup and security considerations, Redis remains a popular choice for applications that require low-latency and high-throughput data access. By following best practices in tuning and security, Redis can be a robust component of your technology stack, offering scalability and reliability for modern application needs.

## References

1. [Redis Official Documentation](https://redis.io/documentation)
2. [Redis Commands Reference](https://redis.io/commands)
3. [Redis Persistence](https://redis.io/topics/persistence)
4. [Redis Replication](https://redis.io/topics/replication)
5. [Redis Sentinel Documentation](https://redis.io/topics/sentinel)
6. [Redis Cluster Specification](https://redis.io/topics/cluster-spec)
7. [Redis Security](https://redis.io/topics/security)
8. [Redis Pub/Sub](https://redis.io/topics/pubsub)
9. [Redis Transactions](https://redis.io/topics/transactions)
10. [Redis Lua Scripting](https://redis.io/commands/eval)
11. [Redis Performance Optimization](https://redis.io/topics/latency)
12. [Redis Memory Optimization](https://redis.io/topics/memory-optimization)
13. [Redis Enterprise Documentation](https://docs.redis.com/latest/rs/)
14. [Redis vs. Memcached](https://aws.amazon.com/elasticache/redis-vs-memcached/)
15. [Redis vs. MongoDB](https://www.mongodb.com/compare/redis-vs-mongodb)
16. [Redis vs. PostgreSQL](https://scalegrid.io/blog/redis-vs-postgresql-which-one-to-choose/)
17. [Redis vs. MySQL](https://scalegrid.io/blog/redis-vs-mysql-a-comparison-of-features-performance-and-use-cases/)
18. [Redis vs. ScyllaDB](https://www.scylladb.com/product/comparison/scylladb-vs-redis/)
19. [Redis Best Practices](https://redislabs.com/redis-best-practices/)
20. [Redis Observability](https://redis.com/redis-enterprise/redis-insight/)
21. [Redis Use Cases](https://redis.com/solutions/use-cases/)
22. [Redis Performance Benchmarks](https://redis.io/topics/benchmarks)
23. [Redis Design Patterns](https://redis.com/redis-best-practices/introduction/)
24. [Redis in Microservices Architecture](https://redislabs.com/blog/redis-microservices-patterns/)
25. [Redis Data Modeling](https://redis.com/redis-best-practices/data-modeling/)

## Presentation

Access the Redis presentation [here](https://docs.google.com/presentation/d/1Wm17qB8OTBqTtzF9kPkm4O_YTSThsDCuj50lH4b9IHM/edit#slide=id.g27a169cc775_2_1).
