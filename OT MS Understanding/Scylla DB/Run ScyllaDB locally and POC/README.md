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

 This POC will showcase standalone ScyllaDB's installation process, basic operations.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | 2 cores                |
| RAM                     | 4GB                    |
| Disk                    | 15GB SSD               |
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

![Screenshot from 2024-09-14 13-21-16](https://github.com/user-attachments/assets/421ee5b6-8266-41ba-8721-675433c23e31)



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

### Step 3:  Now need to install java 11 with below commands
   
```
sudo apt-get install -y openjdk-11-jre-headless
```
```
sudo update-java-alternatives --jre-headless -s java-1.11.0-openjdk-amd64
```

### Step 4: Install ScyllaDB

```bash
sudo apt-get install scylla
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
![Screenshot from 2024-09-16 17-06-07](https://github.com/user-attachments/assets/d5cef51d-2122-427d-8d32-2203cbef1737)



## Basic Operations

Here are some basic CQL commands to get started with ScyllaDB:

1. Connect to ScyllaDB using cqlsh:
   ```bash
   cqlsh -u cassandra -p cassandra
   ```
   ![Screenshot from 2024-09-16 17-05-47](https://github.com/user-attachments/assets/64ac27a9-806a-4d4a-b1ae-df4b7938aeae)



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

ScyllaDB is a robust NoSQL database that excels in performance, scalability, and efficiency. Its design enables it to handle high workloads with low latencies, making it ideal for demanding applications. The database's compatibility with Apache Cassandra ensures a smooth transition for existing users, while its resource-efficient architecture helps in reducing infrastructure costs. Overall, ScyllaDB offers a compelling solution for organizations needing high-performance, scalable, and cost-effective database solutions.

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
