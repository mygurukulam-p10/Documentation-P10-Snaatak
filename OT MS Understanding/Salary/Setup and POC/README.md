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

![image](https://github.com/user-attachments/assets/3ceaca3c-6de1-4534-be4a-1570faf1f104)


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

![image](https://github.com/user-attachments/assets/e79a2a78-de7e-4cf1-9711-e1c17b1f2d4e)


### 2. Now Install ScyllaDB
```
sudo apt-get update
sudo apt-get install scylla
```
![image](https://github.com/user-attachments/assets/6b17265a-4ea3-4064-ab3f-706b3761c412)


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
![image (5)](https://github.com/user-attachments/assets/931cad90-5d55-4029-b321-32177dd82741)



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
![image](https://github.com/user-attachments/assets/6fc1c188-1f74-41ce-86cb-450dc5cca3b2)

### 6. Login as superuser (cassandra)
```
cqlsh -u cassandra -p cassandra
```
### 7. Now create a user in cqlsh with below command,
```
CREATE USER scylla WITH PASSWORD 'password';
```
### 8.give all permissions on keyspace employee_db to the scylla user with below command
```
GRANT ALL PERMISSIONS ON KEYSPACE salary TO scylla;
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
![image (6)](https://github.com/user-attachments/assets/6b4d5fc0-0a19-4e1c-baf5-a93ec1e13691)


## Step 4. Setup Migrate Tool
### 1. Install and check the version
```
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz -o migrate.tar.gz
tar -xvzf migrate.tar.gz
sudo mv migrate.linux-amd64 /usr/local/bin/migrate
sudo chmod +x /usr/local/bin/migrate
migrate -version
```
![Screenshot from 2024-09-07 15-58-08](https://github.com/user-attachments/assets/84905d23-6619-4065-a85f-075ceac2debf)

## Step 5. Seting up the API
### 1. Install JDK 17 & Maven
```
sudo apt install openjdk-17-jdk
java --version
sudo apt install maven
mvn --version
```
![image](https://github.com/user-attachments/assets/ac672659-3a30-46c6-b006-05a7bbeac9a5)


### 2. Edit two files ```application.yml``` and ``` migration.json ```
In ```application.yml```

![image](https://github.com/user-attachments/assets/b657bf0c-0fd5-4376-8b59-64e32441d0a5)

![image](https://github.com/user-attachments/assets/4250675d-adbb-4010-8e16-47b52449ee1b)

In ```migration.json```

![image](https://github.com/user-attachments/assets/b7b752ce-081c-4944-be89-05bf804c5180)

## Step 6. Build Application
### 1. For building the Salary API application, we can use make commands
```
 make build

```
![image (4)](https://github.com/user-attachments/assets/f19a28fc-2260-4baf-bfed-ae713bb34aee)



### 2. To automate the process of applying database migrations in a project, Use this command
```
make run-migrations
```
![image](https://github.com/user-attachments/assets/c8b5a5a1-7ed2-4ce3-89ac-25495ed9c9a2)

### 3. start our application using java runtime
```
java -jar target/salary-0.1.0-RELEASE.jar
```
![image](https://github.com/user-attachments/assets/7cd020bd-198a-4f6d-920a-b615753bdeaf)

### The swagger page will be accessible on
```
http://localhost:8080/salary-documentation
```

![image (8)](https://github.com/user-attachments/assets/303dcf10-d0d5-4820-8cfe-b4215509582b)

![image (7)](https://github.com/user-attachments/assets/d171fba0-28b0-4355-9ed8-c15c2150a01a)



