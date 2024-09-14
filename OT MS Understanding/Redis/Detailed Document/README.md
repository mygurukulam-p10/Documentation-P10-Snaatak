# Redis Documentation

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 06-09-24    | Version 1  | Komal Jaiswal   | 06-09-24       |

## Table of Contents

1. [What is a Database and Cache?](#1-what-is-a-database-and-cache)
2. [Why We Are Learning Redis and the Problems It Addresses](#2-why-we-are-learning-redis-and-the-problems-it-addresses)
3. [Redis vs Alternatives](#3-redis-vs-alternatives)
4. [Key Features of Redis](#4-key-features-of-redis)
5. [Block Architecture of Redis](#5-block-architecture-of-redis)
6. [Types of Redis Architecture](#6-types-of-redis-architecture)
7. [Advantages and Disadvantages](#7-advantages-and-disadvantages)
8. [Conclusion](#8-conclusion)
9. [References](#9-references)

## Purpose

Redis is used in applications to provide high-speed caching, real-time data access, and efficient management of ephemeral data, improving overall performance and scalability.

## 1. What is a Database and Cache?

| **Concept** | **Description**                                                                                                                                                      | **Examples**                |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| **Database** | - Persistent storage system for structured data. <br> - Supports CRUD operations (Create, Read, Update, Delete). <br> - Ensures data integrity and consistency. | MySQL, PostgreSQL, MongoDB |
| **Cache**   | - Temporary storage layer for frequently accessed data. <br> - Improves application performance by reducing database load. <br> - Typically stores data in memory for faster access. | Redis, Memcached           |


## 2. Why We Are Learning Redis and the Problems It Addresses

| **Problem Addressed**         | **Description**                                                                                   |
|-------------------------------|---------------------------------------------------------------------------------------------------|
| **Performance Bottleneck**    | Provides in-memory data storage for high-speed data access, reducing latency in data retrieval.   |
| **Data Caching**              | Efficiently caches frequently accessed data, reducing load on primary databases.                  |
| **Session Management**        | Stores and manages user session data, enabling quick retrieval of session information.            |
| **Real-time Analytics**       | Supports real-time data processing and analysis with suitable data structures.                    |
| **Scalability Challenges**    | Offers clustering and replication for horizontal scaling, supporting high throughput and low latency. |
| **Message Queuing**           | Implements Pub/Sub messaging system to facilitate communication between different application parts. |
| **Data Persistence and Reliability** | Provides data persistence options (RDB and AOF) and supports replication for high availability. |


## 3. Redis vs Alternatives

| **Comparison**       | **Redis**                               | **Memcached**                             | **MongoDB**                                   | **PostgreSQL**                               | **MySQL**                                    | **ScyllaDB**                                 |
|----------------------|-----------------------------------------|-------------------------------------------|-----------------------------------------------|----------------------------------------------|----------------------------------------------|----------------------------------------------|
| **Type**             | In-memory key-value store               | In-memory key-value store                 | Document-oriented database                    | Relational database                          | Relational database                          | Distributed NoSQL database                   |
| **Data Structures**  | Supports more complex data structures (lists, sets) | Primarily supports strings                | Supports complex document structures          | Structured data with tables and relations    | Structured data with tables and relations    | Distributed tables and wide-column store     |
| **Persistence**      | Offers persistence                      | No persistence                            | Supports persistence                          | Full persistence with ACID compliance        | Full persistence with ACID compliance        | Persistence and horizontal scalability       |
| **Replication**      | Supports replication                    | No built-in replication                   | Supports replication                          | Supports replication                         | Supports replication                         | Built-in replication with high availability  |
| **Performance**      | Faster for simple read/write operations | High-speed caching                        | Suitable for complex queries                  | Offers advanced querying capabilities        | Offers ACID compliance for complex transactions | Low-latency access for large distributed datasets |
| **Use Case**         | Best for caching and simple data        | Best for simple caching                   | Handles complex queries and data structures   | Complex transactions and structured data     | Complex, structured data management          | Large-scale data handling and real-time analytics |
| **Setup**            | Simpler setup and management            | Simple setup                              | Requires more configuration for large setups  | Requires more configuration for scaling      | Requires more configuration for scaling      | Better scalability for large datasets        |


## 4. Key Features of Redis

| **Feature**                  | **Description**                                                                                   |
|------------------------------|---------------------------------------------------------------------------------------------------|
| **Data Structures Supported**| Strings, hashes, lists, sets, sorted sets, bitmaps, hyperloglogs, geospatial indexes, and streams. |
| **Pub/Sub Messaging**        | Enables message communication between different parts of an application.                         |
| **Transactions**             | Supports atomic operations using MULTI, EXEC, and DISCARD commands.                              |
| **Lua Scripting**            | Allows execution of custom scripts.                                                              |
| **Replication**              | Master-slave replication for high availability.                                                  |
| **Persistence**              | Options for snapshots and append-only file persistence.                                          |
| **Cluster Mode**             | Supports horizontal scaling and sharding.                                                        |

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


## 7. Advantages and Disadvantages

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

## 8. Conclusion

Redis is a powerful in-memory data structure store that serves as a database, cache, and message broker. It is known for its high performance, versatility in supporting various data structures, and its ability to handle complex use cases like real-time analytics, session management, and message queuing. 

## 9. References

| **Reference**                      | **Link**                                                                                                                             | **Description**                                    |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|
| Redis Official Documentation       | [Redis Documentation](https://redis.io/documentation)                                                                               | Comprehensive guide to Redis features and usage.   |
| Redis Commands Reference           | [Redis Commands](https://redis.io/commands)                                                                                         | Detailed list and explanation of Redis commands.   |
| Redis Persistence                  | [Redis Persistence](https://redis.io/topics/persistence)                                                                            | Information on Redis persistence options.          |
| Redis POC                          | [Redis POC Guide](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Setup%20and%20run%20App%20for%20POC/README.md) | Guide for setting up and running Redis POC.        |

## Presentation

Access the Redis presentation [here](https://docs.google.com/presentation/d/1Wm17qB8OTBqTtzF9kPkm4O_YTSThsDCuj50lH4b9IHM/edit#slide=id.g27a169cc775_2_1).
