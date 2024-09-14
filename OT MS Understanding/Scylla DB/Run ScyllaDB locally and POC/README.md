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
7. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [References](#references)
    

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
| java    | 11      | For running ScyllaDB driver and sample scripts |

### Important Ports

| Inbound Traffic | Description                    |
|-----------------|--------------------------------|
| 9042            | CQL native transport port      |
| 9160            | Thrift client API              |
| 10000           | REST API                       |

## Architecture

ScyllaDB follows a distributed architecture where data is automatically replicated across multiple nodes for fault tolerance and high availability.

![Uploading Screenshot from 2024-09-14 13-21-16.png…]()


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
### Step 4:  Now need to install java 11 with below commands
   
```
sudo apt-get update
```
```
sudo apt-get install -y openjdk-11-jre-headless
```
```
sudo update-java-alternatives --jre-headless -s java-1.11.0-openjdk-amd64
```
### Step 5: Configure ScyllaDB

```bash
sudo scylla_setup
```

Follow the prompts to configure ScyllaDB according to your system specifications.

### Step 6: Start ScyllaDB service

```bash
sudo systemctl start scylla-server
```
![Screenshot from 2024-09-08 00-19-13](https://github.com/user-attachments/assets/6cd720b3-7429-42eb-b438-4ba814f4c168)


### Step 7: Verify ScyllaDB Installation

```bash
nodetool status
```
### Step 8. Configure user Scylla 
Path ` /etc/scylla/scylla.yaml `
```
sudo vi /etc/scylla/scylla.yaml
```
After entering, Edit these entries for security purpose
```
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```
![Screenshot from 2024-09-08 00-23-44](https://github.com/user-attachments/assets/2cb523da-0921-42e3-a621-2cf4faabcb3e)


## Basic Operations

Here are some basic CQL commands to get started with ScyllaDB:

1. Connect to ScyllaDB using cqlsh:
   ```bash
   cqlsh -u cassandra -p cassandra
   ```
   ![Screenshot from 2024-09-08 00-25-56](https://github.com/user-attachments/assets/e33f3204-f741-440b-a906-b250a7fbd42d)


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

## Conclusion

ScyllaDB represents a significant advancement in the world of NoSQL databases, offering a powerful solution for organizations dealing with big data and high-performance requirements. Its key strengths include:

1. **Performance**: ScyllaDB's architecture is designed to maximize hardware utilization, resulting in exceptional performance even under heavy loads. Its ability to handle millions of operations per second with consistently low latencies makes it suitable for demanding use cases.

2. **Scalability**: With its shared-nothing architecture and automatic data distribution, ScyllaDB can easily scale horizontally by adding more nodes to the cluster. This allows organizations to grow their database capacity in line with their needs.

3. **Compatibility**: Being API-compatible with Apache Cassandra, ScyllaDB offers a smooth transition for teams already familiar with Cassandra, while providing performance improvements and easier operations.

4. **Efficiency**: ScyllaDB's resource-efficient design helps organizations reduce their infrastructure costs while maintaining high performance.

5. **Ease of Use**: Despite its powerful features, ScyllaDB maintains a relatively straightforward setup and operation process, as demonstrated in this documentation.

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
