# ScyllaDB Proof of Concept

| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|----------------|----------------|
| Amit Nagar | 09-09-2024 | 1.0 | Amit Nagar | 09-09-2024 |

## Table of Contents

1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
   - [Important Ports](#important-ports)
3. [Architecture](#architecture)
4. [Step-by-step installation of ScyllaDB](#step-by-step-installation-of-scylladb)
5. [Basic Operations](#basic-operations)
6. [Troubleshooting](#troubleshooting)
7. [FAQs](#faqs)
8. [Contact Information](#contact-information)
9. [References](#references)

## Purpose

This proof of concept (POC) aims to demonstrate the capabilities of ScyllaDB, a high-performance NoSQL database that is API-compatible with Apache Cassandra. ScyllaDB is designed to handle big data workloads with high throughput and low latency. This POC will showcase ScyllaDB's installation process, basic operations, and performance characteristics.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | 2 cores                |
| RAM                     | 4GB                    |
| Disk                    | 20GB SSD               |
| OS                      | Ubuntu 22.04 LTS       |

### Dependencies

#### Run time Dependency

| Name    | Version | Description                                    |
|---------|---------|------------------------------------------------|
| Python  | 3.8+    | For running ScyllaDB driver and sample scripts |

### Important Ports

| Inbound Traffic | Description                    |
|-----------------|--------------------------------|
| 9042            | CQL native transport port      |
| 9160            | Thrift client API              |
| 10000           | REST API                       |

## Architecture

ScyllaDB follows a distributed architecture where data is automatically replicated across multiple nodes for fault tolerance and high availability.

![image](https://github.com/user-attachments/assets/96a58199-c89e-4d7c-8875-ade3bf95d98a)

## Step-by-step installation of ScyllaDB

### Step 1: Add ScyllaDB repository

```bash
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```

### Step 2: Update package cache

```bash
sudo apt-get update
```

### Step 3: Install ScyllaDB

```bash
sudo apt-get install scylla
```

### Step 4: Configure ScyllaDB

```bash
sudo scylla_setup
```

Follow the prompts to configure ScyllaDB according to your system specifications.

### Step 5: Start ScyllaDB service

```bash
sudo systemctl start scylla-server
```

### Step 6: Verify ScyllaDB Installation

```bash
nodetool status
```

## Basic Operations

Here are some basic CQL commands to get started with ScyllaDB:

1. Connect to ScyllaDB using cqlsh:
   ```bash
   cqlsh
   ```

2. Create a keyspace:
   ```sql
   CREATE KEYSPACE mykeyspace WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
   ```

3. Use the keyspace:
   ```sql
   USE mykeyspace;
   ```

4. Create a table:
   ```sql
   CREATE TABLE users (
     user_id UUID PRIMARY KEY,
     username TEXT,
     email TEXT
   );
   ```

5. Insert 
   ```sql
   INSERT INTO users (user_id, username, email) 
   VALUES (uuid(), 'amit', 'amit@example.com');
   ```

6. Query 
   ```sql
   SELECT * FROM users;
   ```

## Troubleshooting

- If ScyllaDB service fails to start, check the logs:
  ```bash
  sudo journalctl -u scylla-server
  ```

- For performance issues, use the `nodetool` utility to check cluster status and performance metrics:
  ```bash
  nodetool status
  nodetool tablestats
  ```

- If you encounter connection issues, ensure that the ScyllaDB service is running:
  ```bash
  sudo systemctl status scylla-server
  ```

## FAQs

- **Is ScyllaDB compatible with Cassandra?**  
  Yes, ScyllaDB is API-compatible with Apache Cassandra.

- **Can ScyllaDB be deployed on cloud platforms?**  
  Yes, ScyllaDB can be deployed on major cloud platforms like AWS, GCP, and Azure.

- **Does ScyllaDB support ACID transactions?**  
  ScyllaDB supports lightweight transactions and batch operations, but it's not a fully ACID-compliant database.

## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## References

| Links                                                | Descriptions                             |
|------------------------------------------------------|------------------------------------------|
| [ScyllaDB Documentation](https://docs.scylladb.com/) | Official ScyllaDB documentation          |
| [ScyllaDB Installation Guide](https://docs.scylladb.com/stable/operating-scylla/procedures/install/install-ubuntu.html) | Official installation guide for Ubuntu |
| [ScyllaDB University](https://university.scylladb.com/) | Free online courses on ScyllaDB       |
