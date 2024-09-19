# POC on Liquibase

![l](https://github.com/user-attachments/assets/a707b044-1167-4375-982a-4c20e2b3e0d8)


| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 11-09-24    | version 1  | Vinay Bansal     | 11-09-24       |

## Purpose
We are preparing this document so that we can easily install Liquibase and perform Rollback. Liquibase is a tool designed to help manage and automate database schema changes. Its primary purpose is to handle the version control of database changes, making it easier to track, apply, and revert modifications to a database schema over time.

## Table of Contents
1. [Architecture](#architecture)
2. [Pre-requisites](#pre-requisites)
3. [System Requirements](#system-requirements)
4. [Dependencies](#dependencies)
   * [Run Time Dependencies](#run-time-dependency)
   * [Build Dependencies](#build-dependency)
5. [Important Ports](#important-ports)
6. [Step-by-step installation](#step-by-step-installation)
7. [Rolling Back](#rolling-back-to-a-tag)
8. 
9. [Best Practices](#best-practices)

## Architecture
![liquibase arch](https://github.com/user-attachments/assets/ef7f1555-7369-46ff-9932-9e7acfa7add9)






## Pre-requisites
Install Java(Liquibase is a Java-based tool, so you need to have JDK 8 or higher installed).

## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                    |
| Disk                     |1 GB free disk space                  |
| OS                       | Ubuntu 18.04 LTS         |

## Dependencies
### Run time Dependency
| Name           | Version | Description                                                                                                                         |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| Database       | 14.13   |PostgreSQL is an advanced, open-source relational database management system (RDBMS) known for its robustness, extensibility, and SQL compliance. It is used as the primary database in the Attendance Application |


## Build Dependency
| Name           | Version    | Description        |
| -------------- | ---------- | ------------------ |
| Maven        |  3.6.3   | Integrating Maven with Liquibase automates and streamlines database change management   |

## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 5432            | PostgreSQL      |

## Install git

```
sudo apt install git
```


### Clone the git repository with command 



```
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```


##  Step-by-step installation

### 1. Below Commands to Liquibase

#### Run the following command to import the Liquibase GPG key and add the Liquibase repository to the apt sources list:

  ```
  wget -O- https://repo.liquibase.com/liquibase.asc | gpg --dearmor > liquibase-keyring.gpg && \
cat liquibase-keyring.gpg | sudo tee /usr/share/keyrings/liquibase-keyring.gpg > /dev/null && \
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/liquibase-keyring.gpg] https://repo.liquibase.com stable main' | sudo tee /etc/apt/sources.list.d/liquibase.list
```
  ![Run the following command to import the Liquibase GPG key and add the Liquibase repository to the apt sources list](https://github.com/user-attachments/assets/9f7d846e-4700-4a97-849a-bcdd5caa8c56)

#### Install Liqibase packages.

  ```
  sudo apt-get update
```
  #### Install Liquibase
  ```
  sudo apt-get install liquibase
```
#### Ensure that Liquibase is updated to the desired version:
```
liquibase --version
```
![liquibase version](https://github.com/user-attachments/assets/71f06fdc-ebee-4ff7-845a-789d030fdb2e)


#### Set Liquibase Properties File
- liquibase.properties
- Explanation of Each Property
url: This is the JDBC connection string for your PostgreSQL database. Ensure that the hostname, port, and database name are correct.
driver: Specifies the JDBC driver class for PostgreSQL.
username: The username for connecting to the PostgreSQL database.
password: The password for the specified username.
changeLogFile: The path to your main changelog file, which contains your database changes.

![liquibase p](https://github.com/user-attachments/assets/7f3187a1-a0f7-4216-b882-9342d77614c4)

### Changelog structure 
- Key Components of a Changelog
databaseChangeLog: The root element that encapsulates all changesets.
changeSet: Defines a single atomic change. Each changeset must have a unique id and an author.
changes: A collection of change operations (like createTable, addColumn, etc.) that are part of the changeset.
Rollback: You can define rollback operations within a changeset to specify how to undo the changes.


#### First Changeset
![changeset](https://github.com/user-attachments/assets/103babf4-9839-4873-ba8c-cf76f5353b7c)


#### Integrate Liquibase into your build processes using Maven
![maven pom file](https://github.com/user-attachments/assets/b7b65040-e280-4593-81ba-b780130d8f95)




#### liquibase update

  ```
  mvn liquibase:update
```
![liquibase u1](https://github.com/user-attachments/assets/38aac39b-7e99-44f0-8606-02dc513ba52b)
![liquibase u2](https://github.com/user-attachments/assets/b171f236-339c-401a-9a6c-08fae43cb59f)


#### Add tag 
  
  ```
  liquibase tag v1.0
```
![liquibase t1](https://github.com/user-attachments/assets/c070c5ae-72d3-4a35-80cb-e9a67ec209fe)
![liquibase t2](https://github.com/user-attachments/assets/bd729c73-b8db-4d9e-b774-e6697c2d3771)


#### similarly we create 2 changeset with tag v2.0 and v3.0
![liquibase t3](https://github.com/user-attachments/assets/af08bfa9-9f78-4906-8945-a3f166205a79)


## 1. **Rolling Back to a Tag**
  ```
  liquibase rollback v1.0
```
![liquibase r](https://github.com/user-attachments/assets/3a7770d3-1be7-43c0-878b-175dd60feeac)


 ```
 liquibase history
```
By this we can see is rollback is successful or not
![liquibase r1](https://github.com/user-attachments/assets/b876e2a4-6e9d-4fa9-957b-ba7a962cd6f7)

![liquibase r4](https://github.com/user-attachments/assets/a55cbd6f-d189-4650-a02d-580c0bf9caf0)
![liquibase r5](https://github.com/user-attachments/assets/328b7680-6e6c-4608-9083-09a5ec5de127)



## 2. **Rolling Back by Count**
```
mvn liquibase:update
```
![liquibase h](https://github.com/user-attachments/assets/99db5e35-0c7b-436c-bbb8-caeba0979863)



  ```
  liquibase rollbackCount 1
```
![liquibase r2](https://github.com/user-attachments/assets/ab0ebe7a-d609-4054-a52f-a613a15f079e)



## 3. **Rolling Back to Date**
  ```
liquibase history    
  ```
![liquibase h1](https://github.com/user-attachments/assets/4a1ac51b-a5ee-4540-bf5b-2ec791d2fe74)


```
  liquibase rollbackToDate 2024-09-13T04:38:00
```
![liquibase r3](https://github.com/user-attachments/assets/aee83771-6503-4c41-9809-10f0ca3d5202)



 ```
 liquibase history
```
By this we can see is rollback is successful or not

![liquibase h2](https://github.com/user-attachments/assets/2e4563e3-df8e-476e-8717-cb48cb2bb5e2)


## Identify which author created the changeset. 
Since you cannot filter by author directly via a command, you can capture the output of the history command into a file and then grep through it:
```
liquibase history > changelog_history.txt
grep 'vinay' changelog_history.txt
```
![sidentify](https://github.com/user-attachments/assets/4ae228ce-d620-4ffc-bf5c-02b51f188135)

## Contexts in Liquibase(SQL)
1. create db.changelog-master.sql
2. run liquibase update --contexts=dev command
3. now a table is created with name tes1
![s](https://github.com/user-attachments/assets/cc2f608b-d246-459f-a7e2-d8e78f2fa0b3)
![s1](https://github.com/user-attachments/assets/b7fb6cb5-1f5a-4f25-89ae-c628df4f3bdf)
![s2](https://github.com/user-attachments/assets/baef3d4c-743d-4a14-b1b3-301b131e4b4b)

4. add one more changeset
5. run liquibase update --contexts=prod command
6. now a table is deleted 
![s3](https://github.com/user-attachments/assets/80add126-304a-4cee-b560-2f54a3449add)
![s4](https://github.com/user-attachments/assets/3fe460c8-408d-4452-adce-cb521e1d2519)

## Label
The label filter is a logical expression that you can use to specify one or more changeset labels.
![sl](https://github.com/user-attachments/assets/0fe2fb82-df73-4b7c-9c46-0d066692475d)
![sl1](https://github.com/user-attachments/assets/e549fb5c-452a-406a-a1c5-2fa4f4e6bf2a)


# Best Practices

| **Best Practice**            | **Description**                                                                                                    |
|------------------------------|--------------------------------------------------------------------------------------------------------------------|
| **Version Control**          | Store Liquibase changelog files in version control to track changes and collaborate with your team.                |
| **Incremental Changes**      | Apply changes incrementally and test them in a development environment before deploying to production.             |
| **Use Tags**                 | Tag your changelogs to easily identify and rollback to specific points in your schema history.                     |
| **Modular Changelogs**       | Organize changes into modular changelog files for better readability and maintenance.                              |
| **Automate Updates**         | Integrate Liquibase commands into your CI/CD pipeline to automate database updates during deployments.             |



