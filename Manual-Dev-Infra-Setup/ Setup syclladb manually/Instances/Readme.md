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


### 1.  Now need to install java 11 with below commands
   
### 2. Below Commands to setup scylla db

#### Install a repo file and add the ScyllaDB APT repository to your system.

  ```
  sudo mkdir -p /etc/apt/keyrings
```
  
  ```
  sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
```
  
  ```
  sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```




#### Install ScyllaDB packages.

  ```
  sudo apt-get update
```
  
  ```
  sudo apt-get install -y Scylla
```




#### Now Run the scylla_setup script to tune the system settings and determine the optimal configuration.

  ```
  sudo scylla_setup
```



#### Run ScyllaDB as a service (if not already running).

 ```
 sudo systemctl start scylla-server
```
    

     Run "cqlsh" to check if it connects.


#### then create database named employee_db using below command under cqlsh

CREATE KEYSPACE employee_db 
   WITH REPLICATION = {
   'class' : 'SimpleStrategy', 
   'replication_factor' : 1 
   };


### check if db is created using command "describe keyspaces;"

### make below changes in **/etc/scylla/scylla.yaml **and add below lines at the top of the file

      authenticator: PasswordAuthenticator
      authorizer: CassandraAuthorizer




#### Restart scylla-server with below command


```
sudo systemctl restart scylla-server
```


#### Firstly switch to by default super user of scylla with below command


```
cqlsh -u cassandra -p cassandra;
```


#### Now create a user in cqlsh with below command, 


```
CREATE USER scylla WITH PASSWORD 'password';
```


#### Give all permissions on keyspace employee_db to the scylla user with below command


```
GRANT ALL PERMISSIONS ON KEYSPACE employee_db TO scylla;
```





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

