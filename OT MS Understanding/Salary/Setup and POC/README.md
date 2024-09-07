# SALARY API
|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|06-09-2024|0.1|Brij Singh|Documentation on Salary API|
## Table of Content
- [Purpose](#Purpose)
- [Pre-reqisites](#Pre-requisites)
- [System Requirement](#System-Requirement)
- [Build-Time Dependency](#Build-Time-Dependency)
- [Run-Time Dependency](#Run-Time-Dependency)
- [Important Ports](#important-ports)
- [Architecture ](#Architecture)
## Purpose
The Salary API project is a Java-based microservice designed to manage and process employee salary data. This Application is must be independent and can be run on multiple operating system. JAVA RUNTIME would be required to run this application.
## Pre-requisites
The Salary API application have some database, cache manager and package dependencies. Ensure you have the following on your system :
* [ScyllaDB](https://www.scylladb.com/)
* [Redis](https://redis.io/)
* [Maven](https://maven.apache.org/)
## System Requirements
|Hardware Specification |Minimum Recommendation|
|:-----------------------:|:----------------------:|
|Processor              | Dual-core            |
|RAM                    | 4GB                  |
|Disk                   | 20GB                 |
|OS                     |Ubuntu(22.04)         |
## Build-Time Dependency
| Name | Version | Description |
|:-----:|:------:|:------------:|
|Maven|3.+| It simplifies the management of build procedures, project documentation, and project dependencies.
## Run-Time Dependency
|Name  | Version | Description |
|:------:|:-------:|:----------:|
|JAVA|  17| Running the built Java application is required.|
## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 6379            | Used by Redis      |
| 9042            | Used by ScyllaDB / migrate |
## Architecture
![image](https://github.com/user-attachments/assets/ede77773-b8f7-49a2-b726-4715f51d50e1)

## Install git
```
sudo apt install git
```
## Step 1. Clone the git repository with command
```
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```
###  Step-by-step installation
## Step 2. Below Commands to setup scylla db
#### 1. Install a repo file and add the ScyllaDB APT repository to your system.
  ```
sudo mkdir -p /etc/apt/keyrings
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```
![image](https://github.com/user-attachments/assets/32ed0bdd-03f9-4d1b-bf8e-052688344ea9)


### 2. Now Install ScyllaDB
```
sudo apt-get update
sudo apt-get install scylla
```
![image](https://github.com/user-attachments/assets/e8c3890e-9c34-4f0a-829a-aa53d6929d86)

### 3. Configure ScyllaDB
#### Run the ScyllaDB setup script to configure your installation
```
sudo scylla_setup
```
#image
### 4. Start ScyllaDB & Verify the Installation
```
sudo systemctl start scylla-server
sudo systemctl status scylla-server
```
![image (5)](https://github.com/user-attachments/assets/4dfdf899-abee-4354-be88-e388f82e355a)


### 5. Configure user Scylla & Space
Path ` /etc/scylla/scylla.yaml `
```
sudo vi /etc/scylla/scylla.yaml
```
After entering, Edit these entries for security purpose
```
authenticator: PasswordAuthenticator
authorizer: CassandraAuthorizer
```
### 6. Login as superuser (cassandra)
```
cqlsh -u cassandra -p cassandra
```
### 7. Create ScyllaDB user & give permission to create keyspace
```
CREATE ROLE scylladb WITH PASSWORD = 'cassandra' AND LOGIN = true;
GRANT CREATE ON ALLKEYSPACE TO scylladb;
exit
```
#image
### Login with scyllaDB User and create a keyspace
```
to add
```
## Step 3. Setup Redis Server
### 1. Install Redis and test
```
sudo apt update
sudo apt install -y redis-server
sudo systemctl start redis-server
sudo systemctl status redis-server
redis-cli
```
![image (6)](https://github.com/user-attachments/assets/edb58484-e14a-4be7-afff-fe9017d59d19)

## Step 4. Setup Migrate Tool
### 1. Install and check the version
```
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz -o migrate.tar.gz
tar -xvzf migrate.tar.gz
sudo mv migrate.linux-amd64 /usr/local/bin/migrate
sudo chmod +x /usr/local/bin/migrate
migrate -version
```
#image
## Step 5. Seting up the API
### 1. Install JDK 17 & Maven
```
sudo apt install openjdk-17-jdk
java -version
sudo apt install maven
mvn -version
```
#image
### 2. Edit two files ```application.yml``` and ``` migration.json ```
In ```application.yml```
#image
In ```migration.json```
## Step 6. Build Application
### 1. For building the Salary API application, we can use make commands
```
make build
```
![image](https://github.com/user-attachments/assets/1c59ce2a-a505-417e-a819-365a72a5a24d)

### 2. To automate the process of applying database migrations in a project, Use this command
```
make run-migrations
```
### 3. start our application using java runtime
```
![image](https://github.com/user-attachments/assets/fee622fd-b174-44fb-a168-eb16e2a7f940)


java -jar target/salary-0.1.0-RELEASE.jar
```
![image](https://github.com/user-attachments/assets/4242ad6d-eba5-495d-a244-dcce7f1c47cb)

ScyllaDBScyllaDB
Home
ScyllaDB is the distributed database for data-intensive apps that require high performance and low latency. (79 kB)
https://www.scylladb.com/

RedisRedis
Redis - The Real-time Data Platform
Developers love Redis. Unlock the full potential of the Redis database with Redis Enterprise and start building blazing fast apps. (12 kB)
https://redis.io/

GitHubGitHub
salary-api/static/salary.png at main · OT-MICROSERVICES/salary-api
Java microservice for handling all attendance related data - OT-MICROSERVICES/salary-api (50 kB)
https://github.com/OT-MICROSERVICES/salary-api/blob/main/static/salary.png

GitHubGitHub
GitHub - OT-MICROSERVICES/employee-api: A Golang based web microservice for handling all employee related data
A Golang based web microservice for handling all employee related data - OT-MICROSERVICES/employee-api (54 kB)
https://github.com/OT-MICROSERVICES/employee-api.git

