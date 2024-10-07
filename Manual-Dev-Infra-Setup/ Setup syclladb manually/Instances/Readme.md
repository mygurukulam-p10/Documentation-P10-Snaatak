# 🚀 ScyllaDB Manual Setup

| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 04-10-2024   | 1.0     | Amit Nagar      | 08-10-2024      |

---

## 📑 Table of Contents

1. [📌 Purpose](#-purpose)
2. [🛠️ Pre-requisites](#-pre-requisites)
   - [💻 System Requirements](#-system-requirements)
   - [📦 Dependencies](#-dependencies)
   - [🔗 Important Ports](#-important-ports)
3. [⚙️ Step-by-step Installation of ScyllaDB](#️-step-by-step-installation-of-scylladb)
4. [📧 Contact Information](#-contact-information)
5. [📚 References](#-references)

---

## 📌 Purpose

This document outlines the process for manually installing ScyllaDB in a standalone environment.

---

## 🛠️ Pre-requisites

### 💻 System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | 2 cores                |
| RAM                     | 4GB                    |
| Disk                    | 15GB SSD               |
| OS                      | Ubuntu 22.04 LTS       |

### 📦 Dependencies

#### Run-time Dependency

| Name    | Version | Description                                    |
|---------|---------|------------------------------------------------|
| Java    | 11      | Required for running ScyllaDB driver and sample scripts |

### 🔗 Important Ports

| Inbound Traffic | Description               |
|-----------------|---------------------------|
| 9042            | CQL native transport port |

---

## ⚙️ Step-by-step Installation of ScyllaDB
### Step 1: Add ScyllaDB repository

```bash
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```
![Screenshot from 2024-10-08 02-31-29](https://github.com/user-attachments/assets/a1396798-7743-477a-be6e-9a3c1b35ad03)

### Step 2: Update package cache

```bash
sudo apt-get update
```

### Step 3:  Now need to install java 11 with below commands
   
```
sudo apt-get install -y openjdk-11-jre-headless
```

![Screenshot from 2024-10-08 02-32-44](https://github.com/user-attachments/assets/d72a5007-fbab-412b-a041-f5cdf62c1734)

```
sudo update-java-alternatives --jre-headless -s java-1.11.0-openjdk-amd64
```
![Screenshot from 2024-10-08 02-33-15](https://github.com/user-attachments/assets/df7b868b-20ab-477b-b66f-817d32da30a2)

### Step 4: Install ScyllaDB

```bash
sudo apt-get install scylla
```
![Screenshot from 2024-10-08 02-37-00](https://github.com/user-attachments/assets/3824a62f-d378-4b9e-8db6-9c5b2ceebb6e)

### Step 5: Configure ScyllaDB

```bash
sudo scylla_setup
```
![Screenshot from 2024-10-08 02-39-55](https://github.com/user-attachments/assets/44da817c-5a3d-45ae-b603-5e87671020f8)
![Screenshot from 2024-10-08 02-40-50](https://github.com/user-attachments/assets/a9130cec-09ca-4069-87e9-73a98744ea88)
![Screenshot from 2024-10-08 02-42-32](https://github.com/user-attachments/assets/0c2d319e-4bb2-440d-b6fd-a54970b914ee)


Follow the prompts to configure ScyllaDB according to your system specifications.

### Step 6: Start ScyllaDB service and check its status

Start the ScyllaDB service:

```bash
sudo systemctl start scylla-server

```
Check the status of the ScyllaDB service

```bash
sudo systemctl status scylla-server

```

![Screenshot from 2024-10-08 02-48-36](https://github.com/user-attachments/assets/d1facbb8-35fa-455b-989a-d16847e8311a)


### Step 7: Verify ScyllaDB Installation

```
 Use nodetool to check the status of your ScyllaDB nodes
```
```bash
nodetool status
```
![Screenshot from 2024-10-08 02-49-24](https://github.com/user-attachments/assets/24e99352-967f-4bab-ad56-7475ae1c7676)

### Step 8. Configure user Scylla 
```
sudo vi /etc/scylla/scylla.yaml
```
After entering, Edit these entries for security purpose
```
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```
![Screenshot from 2024-10-08 02-56-58](https://github.com/user-attachments/assets/493adee9-ad6a-466d-903a-60897f2e27fc)

### Authentication and Authorization in ScyllaDB

#### `authenticator: PasswordAuthenticator`
- **Purpose**: Specifies the method used for authentication in ScyllaDB.
- **Description**: The `PasswordAuthenticator` setting means that users must provide a username and password to authenticate. It uses a password-based authentication method, where credentials are checked against the stored user data.

#### `authorizer: CassandraAuthorizer`
- **Purpose**: Defines the authorization method used in ScyllaDB.
- **Description**: The `CassandraAuthorizer` setting allows you to control access to database resources using roles and permissions. It is similar to how Apache Cassandra manages authorization and helps in defining who can access what data and perform what operations.


## Basic Operations

Here are some basic CQL commands to get started with ScyllaDB:

1. Connect to ScyllaDB using cqlsh:
   ```bash
   cqlsh -u cassandra -p cassandra
   ```
  ![Screenshot from 2024-10-08 03-25-27](https://github.com/user-attachments/assets/2c96db4a-c9f3-42d3-9973-768084b4982f)


2. Create a keyspace:
   ```sql
   CREATE KEYSPACE employee_db WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
   ```
   ![Screenshot from 2024-10-08 03-26-18](https://github.com/user-attachments/assets/c5c89f26-59de-4aed-8c7f-7d2d9fa2a750)


## 📞 Contact Information

| 👤 **Name**     | 📧 **Email Address**                                                   |
|-----------------|-----------------------------------------------------------------------|
| **Amit Nagar**  | [amit.nagar.snaatak@mygurukulam.com](mailto:amit.nagar.snaatak@mygurukulam.com) |

---

## 🔗 References

| 🌐 **Links**                                                                                     | 📄 **Descriptions**                                    |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| [📘 ScyllaDB Documentation](https://docs.scylladb.com/)                                         | Official ScyllaDB documentation                        |
| [🔧 ScyllaDB Installation Guide](https://docs.scylladb.com/stable/operating-scylla/procedures/install/install-ubuntu.html) | Official installation guide for Ubuntu                 |
| [🎓 ScyllaDB University](https://university.scylladb.com/)                                      | Free online courses to get started with ScyllaDB       |

