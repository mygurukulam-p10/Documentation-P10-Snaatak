# 💼 Salary API

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 06-09-2024         | 0.2        | Brij Singh   | Documentation on Salary API    |



## 📑 Table of Contents

- [🔍 Purpose](#-purpose)
- [⚙️ Pre-requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🛠️ Build-Time Dependency](#-build-time-dependency)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🌐 Important Ports](#-important-ports)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📧 Contact Information](#-contact-information)

---

## 🔍 Purpose

The **Salary API** is a Java-based microservice designed to manage and process employee salary data. The application is platform-independent and can run on multiple operating systems. The only requirement is that the **Java Runtime Environment (JRE)** is installed to run the application.

---

## ⚙️ Pre-requisites

The Salary API requires the following dependencies for operation:

- [ScyllaDB](https://www.scylladb.com/) - Database storage.
- [Redis](https://redis.io/) - Cache manager.
- [Maven](https://maven.apache.org/) - Build automation tool.

---

## 🖥️ System Requirements

| 💻 Hardware Specification | ⚙️ Minimum Recommendation |
|---------------------------|----------------------------|
| **Processor**              | Dual-core                  |
| **RAM**                    | 4GB                        |
| **Disk**                   | 20GB                       |


---

## 🛠️ Build-Time Dependency

| 🛠️ Name | 📦 Version | 📄 Description |
|---------|------------|----------------|
| **Maven** | 3.+      | Simplifies build management, project documentation, and dependency management. |

---

## 🚀 Run-Time Dependency

| 🚀 Name | 📦 Version | 📄 Description          |
|---------|------------|--------------------------|
| **Java** | 17        | Required to run the built Java application. |

---

## 🌐 Important Ports

| 🔌 Inbound Traffic | 📄 Description           |
|--------------------|--------------------------|
| **6379**           | Used by Redis            |
| **9042**           | Used by ScyllaDB / migrate |

---

## 🏗️ Architecture

![image](https://github.com/user-attachments/assets/3ceaca3c-6de1-4534-be4a-1570faf1f104)



## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
## Step 2. Below Commands to setup scylla db
#### 1. Install a repo file and add the ScyllaDB APT repository to your system.
  ```
sudo mkdir -p /etc/apt/keyrings
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```

![image](https://github.com/user-attachments/assets/e79a2a78-de7e-4cf1-9711-e1c17b1f2d4e)


### 2️⃣ Install ScyllaDB
```
sudo apt-get update
sudo apt-get install scylla
```
![image](https://github.com/user-attachments/assets/6b17265a-4ea3-4064-ab3f-706b3761c412)


#### 3️⃣ Configure ScyllaDB
#### Run the ScyllaDB setup script to configure your installation
```
sudo scylla_setup
```
#### 4️⃣ Start ScyllaDB & Verify Installation
```
sudo systemctl start scylla-server
sudo systemctl status scylla-server
```
![image (5)](https://github.com/user-attachments/assets/931cad90-5d55-4029-b321-32177dd82741)



#### 5️⃣ Configure User and Keyspace
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

### 6️⃣ Login as superuser (cassandra)
```
cqlsh -u cassandra -p cassandra
```
![Screenshot from 2024-09-13 02-40-46](https://github.com/user-attachments/assets/2d2148dc-efee-4a7f-aca2-79a4be459dc6)

### 7. Now create a user in cqlsh with below command,
```
CREATE USER scylla WITH PASSWORD 'password';
```
![image](https://github.com/user-attachments/assets/6c2b4611-fab3-49a7-ad92-66957bab98cc)


### 8.give all permissions on keyspace employee_db to the scylla user with below command
```
GRANT ALL PERMISSIONS ON KEYSPACE salary TO scylla;
```

![image](https://github.com/user-attachments/assets/017ec23a-b09b-4109-93ce-c80ba6b02c9b)


### 💽 Step 3: Setting up Redis
#### 1️⃣ Install Redis and Test
```
sudo apt update
sudo apt install -y redis-server
sudo systemctl start redis-server
sudo systemctl status redis-server
redis-cli
```
![image (6)](https://github.com/user-attachments/assets/6b4d5fc0-0a19-4e1c-baf5-a93ec1e13691)


### 💽 Step 4: Setup Migrate Tool

#### 1️⃣ Install and Check Version
```
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz -o migrate.tar.gz
tar -xvzf migrate.tar.gz
sudo mv migrate.linux-amd64 /usr/local/bin/migrate
sudo chmod +x /usr/local/bin/migrate
migrate -version
```
![Screenshot from 2024-09-07 15-58-08](https://github.com/user-attachments/assets/84905d23-6619-4065-a85f-075ceac2debf)

### 💽 Step 5: Setup the API
#### 1️⃣ Install JDK 17 and Maven
```
sudo apt install openjdk-17-jdk
java --version
sudo apt install maven
mvn --version
```
![image](https://github.com/user-attachments/assets/ac672659-3a30-46c6-b006-05a7bbeac9a5)


#### 2️⃣ Configure `application.yml` and `migration.json`
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



## 📧 Contact Information

For any queries or further information, feel free to contact:

| 📛 Name       | ✉️ Email Address                    |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |
