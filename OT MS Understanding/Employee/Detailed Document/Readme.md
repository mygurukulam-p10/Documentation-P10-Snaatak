# Employee API Detailed Document

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi       | 06-09-24    | Version 1  | Megha Tyagi   | 06-09-24       |

This README provides an overview of the technology stack used in our Attendance API project. Each section includes features, pros and cons, and relevant resources.

## Table of Contents
1. [Redis](#1-redis)
2. [Migrations](#2-migrations)
3. [ScyllaDB](#3-scylladb)
4. [Java](#4-java)
5. [Golang](#5-golang)
6. [Swagger UI](#6-swagger-ui)


## 1. Redis

"Redis (which stands for REmote DIctionary Server)is an open-source in-memory data structure store that also can be used as a database as well as caching. It supports almost all types of data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps. Redis also can be used for messaging systems used as pub/sub".

### Features:
- In-memory data structure store
- Supports various data structures (strings, hashes, lists, sets, etc.)
- Provides pub/sub messaging system
- Offers data persistence options
- Includes built-in replication and cluster mode

| Pros                                         | Cons                                                 |
|----------------------------------------------|------------------------------------------------------|
| Extremely fast read/write operations         | Limited storage capacity (bound by RAM)              |
| Reduces database load by caching data        | Data can be lost if not configured for persistence   |
| Supports distributed locking and session management | Less suitable for complex queries compared to relational databases |
| Lightweight and easy to set up               |                                                      |
| Versatile for various use cases beyond caching |                                                      |


### Why use Redis?

1. #### Super-fast speed -
   Redis is blazingly fast! This is due to the fact that it has been written in the C language.


2. #### Pub/Sub -
   The use cases for Pub/Sub are truly boundless. I’ve seen people use it for social network connections, for triggering scripts based 
   on Pub/Sub events, and even a chat 
   system built using Redis Pub/Sub


3. #### NoSQL Database –
   Redis is a NoSQL Database.


4. #### Queues -
   Taking advantage of Redis’ in memory storage engine to do list and set operations makes it an amazing platform to use for a message 
   queue.


5. #### Session Cache -
   One of the most apparent use cases for Redis is using it as a session cache. The advantages of using Redis over other session 
   stores, such as Memcached, is that Redis 
   offers persistence.


6. #### Full Page Cache (FPC) -
   Redis provides a very easy FPC platform to operate in. Going back to consistency, even across restarts of Redis instances, with 
   disk persistence your users won’t see a 
   decrease in speed for their page loads—a drastic change from something like PHP native FPC.


7. #### Popular usage -
   Currently, it is being used by tech-giants like GitHub,Weibo, Pinterest, Snapchat, Craigslist, Digg, StackOverflow, Flickr.


8. #### Developer friendly -
   Redis is being supported in most of the languages (Perks of using an Open Source Technology). Languages like JavaScript, Java, Go, 
   C, C++, C#, Python, Objective-C, PHP 
   and almost every famous language out there has support for this.


  Below mentioned are some of the most important reasons why one should try Redis at least once.
   
   ### Relevant Resources:
  - [Redis Official Documentation](https://redis.io/documentation)
  - [Redis: Beyond Simple Caching](https://redis.com/blog/redis-beyond-caching/)
  - [Redis vs Memcached: Which One to Choose?](https://aws.amazon.com/elasticache/redis-vs-memcached/)

## 2. Migrations
The migrate tool is a database migration tool that helps you manage and apply schema changes to your databases in a controlled and 
consistent manner. It's especially 
useful for DevOps and software development teams that frequently update their database schemas. The migrate tool is open-source 
and supports a variety of databases, such as PostgreSQL,more.

### Key Features of the migrate Tool:
    
  1. #### Multi-database Support: 
     It supports multiple databases, allowing you to apply migrations across different database systems. This makes it versatile for 
     projects involving multiple databases.

  2. #### Version Control for Schema: 
     You can keep track of different versions of your database schema, making it easy to roll back or upgrade to a specific version.

  3.  #### CLI and Library: 
      The tool can be used both as a command-line interface (CLI) and as a library, providing flexibility for automation and 
      integration with other tools or 
      systems.

  4. #### Idempotent Migrations: 
     Ensures that the same migration can be safely run multiple times without causing errors or inconsistencies in the database.


  5. ### Comman Use Cases:
   
      (i) Applying schema changes across different environments (development, staging, production).
  
      (ii) Automating the process of schema migration during CI/CD pipelines.
    
      (iii) Reverting changes in case of errors or when a rollback is required.

  ### Relevant Resources:
 
  - [Migrate:stackoverflow docs](https://stackoverflow.com/questions/tagged/migrate))
  - [Migrate Github Docs](https://github.com/golang-migrate/migrate)
  - [Migrate CLI](https://github.com/golang-migrate/migrate/blob/master/cmd/migrate/README.md)

 ## 3. ScyllaDB

   ScyllaDB is a high-performance, distributed NoSQL database designed to be a drop-in replacement for Apache Cassandra. It is 
   designed to handle large-scale data and provide high availability, scalability, and low latency. ScyllaDB is written in C++ and 
   optimized to leverage modern hardware efficiently, making it known for its high performance compared to other NoSQL databases.

 ### Features: 
   1. #### High Performance:
   ScyllaDB is known for its low latency and high throughput, achieved through efficient use of system resources and a highly 
   optimized codebase written in C++.

   2. ### Horizontal Scalability:
   It supports easy scaling by adding more nodes to the cluster, which helps in handling increasing workloads and data volumes 
   seamlessly.

   3. ### Automatic Sharding: 
   ScyllaDB automatically manages data distribution and balancing across nodes in the cluster, reducing the operational overhead.

   4. ### Advanced Consistency Models: 
   It provides tunable consistency levels, allowing you to balance between consistency and performance based on your application's 
   requirements.

   5. ### Schema Management: 
   ScyllaDB supports dynamic schema changes without downtime, making it easier to evolve your data model over time.

   6. ### Built-in Monitoring:
   It includes tools and metrics for monitoring and managing the health and performance of the database.

   7. ### Compatibility with Cassandra:
   ScyllaDB is compatible with Apache Cassandra's Query Language (CQL) and its client drivers, allowing for an easier transition from 
   Cassandra.

### Why Use ScyllaDB?
1.  #### Performance:
    ScyllaDB offers better performance and lower latency compared to Apache Cassandra due to its optimized code and efficient use of 
    hardware.

2.  #### Scalability:
    It provides effortless scaling with minimal manual intervention, making it suitable for applications with growing data needs.

3. #### Cost Efficiency:
   Due to its high performance and efficient use of resources, ScyllaDB can be more cost-effective in terms of infrastructure 
   requirements compared to other NoSQL databases.

4. #### High Availability:
   It ensures high availability and fault tolerance, which is crucial for mission-critical applications that require continuous 
   operation.

5. #### Ease of Use:
   Its compatibility with Cassandra makes it easier for teams already using Cassandra to migrate or adopt ScyllaDB without significant 
   changes to their applications.
   
### Relevant Resources:
- [ScyllaDB Homepage Documentation](https://www.scylladb.com/)
- [Stackoverflow](https://stackoverflow.com/questions/tagged/scylla?tab=Newest)

                                                  
## 4. Java

### Features:
- Object-oriented programming language
- Platform-independent ("Write Once, Run Anywhere")
- Strong typing and compile-time error checking
- Extensive standard library and third-party ecosystem
- Supports multithreading and concurrent programming

| Pros                                         | Cons                                                 |
|----------------------------------------------|------------------------------------------------------|
| Highly scalable and performant for enterprise applications | Can be verbose compared to some modern languages      |
| Strong community support and extensive documentation | Slower startup times compared to languages like Go or Node.js |
| Excellent tools for testing, debugging, and profiling | Higher memory usage compared to lower-level languages |
| Well-suited for building robust backend services |                                                      |

### Relevant Resources:
- [Java Official Documentation](https://docs.oracle.com/en/java/)
- [Building RESTful APIs with Spring Boot](https://spring.io/guides/tutorials/rest/)
- [Java vs Kotlin: Which is Better for Android App Development?](https://www.netguru.com/blog/java-vs-kotlin)

## 5. Golang 
Go, also known as Golang, is an open-source programming language developed by Google in 2007 and released in 2009. It is designed to be simple, efficient, and reliable, combining the ease of development found in dynamically typed languages with the performance and safety of statically typed languages. Go is particularly known for its concurrency model, which allows developers to write concurrent programs easily, making it suitable for building scalable and high-performance applications.

### Features of Go: 
1. #### Static Typing and Efficiency:
   Go is statically typed, which means that type errors are caught at compile time, leading to safer and more reliable code.

2. #### Concurrency Support:
   Go's goroutines and channels provide a simple and efficient model for concurrency, which is essential for modern cloud-native and 
   distributed applications.

3. #### Garbage Collection:
   Go includes automatic garbage collection, which helps manage memory efficiently without manual intervention.

4. #### Built-in Testing Framework:
   Go provides a built-in testing framework (testing package), making it easier to write unit tests, benchmarks, and examples.

5. #### Native Compilation:
   Go compiles to native machine code, allowing applications to run with minimal runtime overhead, making them efficient and fast.

6. #### Dependency Management:
   The Go modules system simplifies dependency management and versioning, making it easier to build and distribute Go applications.

7. #### Tooling and Ecosystem:
   Go has excellent tooling support, including gofmt for formatting, go build for compiling, and go mod for dependency management.


### Relevant Resources:
- [Go Official Documentation](https://go.dev/doc/)
- [Awesome Go](https://awesome-go.com/)

## 6. Swagger UI

### Features:
- Interactive API documentation and testing tool
- Automatically generates documentation from OpenAPI specifications
- Provides a user-friendly interface for exploring API endpoints
- Supports both RESTful and SOAP web services
- Customizable with themes and plugins

| Pros                                         | Cons                                                  |
|----------------------------------------------|-------------------------------------------------------|
| Easy to set up and integrate with Python-based APIs | Can add extra steps to the API development workflow    |
| Improves developer experience with interactive API exploration | May expose internal API details if not configured properly |
| Supports live testing of API endpoints       | Limited styling options compared to custom documentation solutions |
| Automatically updates with API changes       |                                                       |

### Relevant Resources:
- [Swagger UI Documentation](https://swagger.io/tools/swagger-ui/)
- [Getting Started with Swagger UI](https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/)
- [Best Practices for Using Swagger UI](https://swagger.io/resources/articles/best-practices-in-api-documentation/)


![Employee_API Architecture drawio](https://github.com/user-attachments/assets/5b87b48d-8399-4ac7-8d49-361de4189828)

