# PostgreSQL 

|     Author    | Created on | Version | Last updated by | Last edited on |
|---------------|------------|---------|-----------------|----------------|
| Abhinav Singh | 09-09-2024 |   1.0   |  Abhinav Singh  |   11-09-2024   |

## Table of Contents

1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
   - [Important Ports](#important-ports)
3. [Architecture](#architecture)
4. [Features](#features)
5. [Detailed Explanation of PostgreSQL](#detailed-explanation-of-PostgreSQL)
6. [Step-by-step installation of PostgreSQL](#step-by-step-installation-of-PostgreSQL)
7. [Basic Operations](#basic-operations)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [References](#references)    

## Purpose

This proof of concept (POC) demonstrates the capabilities of PostgreSQL, a powerful open-source relational database system known for its performance, reliability, and feature set. PostgreSQL is widely used for transactional and analytical workloads, supporting advanced SQL features, extensibility, and robust ACID compliance.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | 2 cores                |
| RAM                     | 4GB                    |
| Disk                    | 20GB SSD               |
| OS                      | Ubuntu 24.04 LTS       |

### Dependencies

#### Run time Dependency

|   Name   | Version |                  Description                   |
|----------|---------|------------------------------------------------|
| libpq    |  Latest |              PostgreSQL C API library          |

### Important Ports

| Inbound Traffic |              Description               |
|-----------------|----------------------------------------|
| 5432            |    PostgreSQL default database port    |

## Architecture

PostgreSQL follows a client-server architecture, where each client connection is handled by a separate process. Data is stored in a structured format and can be accessed via SQL queries. PostgreSQL supports advanced features like MVCC (Multiversion Concurrency Control), foreign keys, and triggers.
![image](https://github.com/user-attachments/assets/8bf267b4-6199-46d1-a0dd-a07fe6a64769)

### Features
- Fully ACID-compliant transactions.
- Support for advanced data types (JSON, Arrays, XML).
- Extensible with custom functions and plugins.
- Multi-version concurrency control (MVCC).
- Replication and high availability features
- Support for full-text search.
- Advanced indexing techniques (B-tree, GIN, GIST)

|                      Pros                    |                             Cons                                |
|----------------------------------------------|-----------------------------------------------------------------|
|    Excellent support for complex queries     |                 Can be resource-intensive at scale              |
|    Strong consistency and data integrity     |    More difficult to scale horizontally than NoSQL databases    |
|    Open-source with an active community      | Manual tuning required for optimal performance |

## Detailed Explanation of PostgreSQL

PostgreSQL is a highly reliable and robust open-source relational database that supports a wide range of applications, from web services to large-scale data analytics.

1. **Architecture**: 
   PostgreSQL uses a process-based architecture where every client connection is assigned its own process. The data is stored in structured tables with support for ACID-compliant transactions. PostgreSQL offers logical and streaming replication, providing various high-availability options.

2. **Performance Optimizations**:
   - **Query Planner**: PostgreSQL features an advanced query planner and optimizer, ensuring efficient execution of queries.
   
   - **Indexing**: Support for a variety of index types allows for faster data retrieval, even with large datasets.
   
   - **Parallel Query Execution**: PostgreSQL can execute queries in parallel, improving performance for large datasets.
   

5. **Advanced Features**:
   - **Stored Procedures**: Custom functions written in PL/pgSQL, Python, or other languages.
   - **Foreign Data Wrappers**: Ability to query other databases and systems from within PostgreSQL.
   - **Logical Replication**: Allows selective replication of data between PostgreSQL instances.
   - **Partitioning**: Support for table partitioning, which improves performance and manageability.

6. **Monitoring and Management**:
   PostgreSQL provides robust monitoring and management tools to ensure the health and performance of the database like pg_stat_activity, pg_stat_user_tables, pgAdmin, Prometheus and Grafana integration.
7. **Use Cases**:
   PostgreSQL is highly versatile and suitable for a wide range of applications across various industries:
   - Transactional systems
   - Data warehousing
   - Geospatial applications
   - Financial services
   - Content management systems (CMS)
   - Enterprise applications

8. **Cloud and Kubernetes Support**:
   PostgreSQL is highly adaptable for cloud-native and containerized environments.

By leveraging its flexible deployment options and cloud-native compatibility, PostgreSQL can be seamlessly integrated into modern infrastructure architectures.

## Step-by-step installation of PostgreSQL

### Update the package list and upgrade existing packages-with-command

```
sudo apt update && sudo apt upgrade -y
```

## Install PostgreSQL along with postgresql-contrib, which adds useful tools for database management.

```
sudo apt install postgresql postgresql-contrib -y
```

### Start the PostgreSQL service and ensure it runs at startup

```
sudo systemctl start postgresql
sudo systemctl enable postgresql
```

### Verify that PostgreSQL is running

```
sudo systemctl status postgresql
```

### PostgreSQL creates a user named postgres by default. Switch to this user to interact with PostgreSQL

```
sudo -i -u postgres
```
### Once logged in as postgres user, you can access the PostgreSQL shell with below command

```
psql
```
## Basic Operations

Here are some basic SQL commands to get started with PostgreSQL

## Inside the PostgreSQL shell, you can create a new database user and a new database

### To create a new user use command

```
CREATE USER myuser WITH PASSWORD 'mypassword';
```

### To create a new database
 
```
CREATE DATABASE mydb OWNER myuser;
```

### To Grant all privileges on the database to the user-
```
GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```

### You can now test the connection to the new PostgreSQL database
```
psql -U myuser -d mydb -h 127.0.0.1 -W
```

### To create a table inside the created database mydb
```
CREATE TABLE mytable (ID SERIAL PRIMARY KEY,name VARCHAR(100),type VARCHAR(50));
```

### To insert values in the created table mytable
```
INSERT INTO mytable (ID, name, type) 
VALUES (1, 'John Doe', 'Employee');
```

### To fetch all values from table created
```
select * from mytable
```

## Conclusion

PostgreSQL is an open-source, feature-rich relational database that excels in various use cases, from transactional systems to large-scale analytics. Its extensibility, reliability, and cloud-native capabilities make it a top choice for modern applications.

## Contact Information

|    Name       |               Email address           |
|---------------|---------------------------------------|
| Abhinav Singh | abhinav.singh.snaatak@mygurukulam.com |

