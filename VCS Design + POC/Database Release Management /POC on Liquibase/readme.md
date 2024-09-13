# POC on Liquibase

![liquibase](https://github.com/user-attachments/assets/5534b57c-9cf3-4fcc-8040-3665ed0a8c0d)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 11-09-24    | version 1  | Vinay Bansal     | 11-09-24       |

## Purpose
Liquibase is a tool designed to help manage and automate database schema changes. Its primary purpose is to handle the version control of database changes, making it easier to track, apply, and revert modifications to a database schema over time.

## Table of Contents
1. [Architecture](#architecture)
2. [Pre-requisites](#pre-requisites)
3. [System Requirements](#system-requirements)
4. [Dependencies](#dependencies)
   * [Run Time Dependencies](#run-time-dependency)
   * [Build Dependencies](#build-dependency)
5. [Important Ports](#important-ports)
6. [Repo clone](#clone-the-git-repository-with-command) 
7. [Step-by-step installation](#step-by-step-installation)

## Architecture
![liquibase arch](https://github.com/user-attachments/assets/ffac290d-4ff9-405e-8a10-08d74d73abd4)




## Pre-requisites
Install Java(Liquibase is a Java-based tool, so you need to have JDK 8 or higher installed).

## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 20GB                   |
| OS                       | Ubuntu(22.04)          |

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
  ![Run the following command to import the Liquibase GPG key and add the Liquibase repository to the apt sources list](https://github.com/user-attachments/assets/49af7288-e3c1-4523-a1f3-93ddf2f3e9a5)
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
![liquibase version](https://github.com/user-attachments/assets/acf660d7-c612-45fa-ba60-c70b41e62294)

#### Set Liquibase Properties File
- liquibase.properties

![liquibase p](https://github.com/user-attachments/assets/8966202f-df6c-4ca1-8ca7-93db5e0c0689)


#### First Changeset
![changeset](https://github.com/user-attachments/assets/0c40031d-4ebc-4cd2-9d49-fafad1d667f8)

#### Integrate Liquibase into your build processes using Maven
![maven pom file](https://github.com/user-attachments/assets/8d46ca81-fe53-41e8-8ffd-d2ed3ae4ea92)



#### liquibase update

  ```
  mvn liquibase:update
```
![liquibase u1](https://github.com/user-attachments/assets/1719f314-6ed4-49a6-b465-5bddfb609b91)
![liquibase u2](https://github.com/user-attachments/assets/ede74da6-0a96-485e-8b89-d6a6dba1da1b)

#### Add tag 
  
  ```
  liquibase tag v1.0
```
![liquibase t1](https://github.com/user-attachments/assets/0ae74428-6265-48e8-98fe-b9a96ec7db9e)
![liquibase t2](https://github.com/user-attachments/assets/39156f58-9156-45a7-9aea-8f7278dc4925)





#### similarly we create 2 changeset with tag v2.0 and v3.0
![liquibase t3](https://github.com/user-attachments/assets/201b1afd-82a0-4d10-aed3-1f066d76b296)

## 1. **Rolling Back to a Tag**
  ```
  liquibase rollback v1.0
```
![liquibase r](https://github.com/user-attachments/assets/a048f548-38d4-47de-88e1-eb0605acfb52)

 ```
 liquibase history
```
By this we can see is rollback is successful or not
![liquibase r1](https://github.com/user-attachments/assets/58c9112f-848e-47eb-add3-d72fd684985f)

## 2. **Rolling Back by Count**
```
mvn liquibase:update
```
![liquibase h](https://github.com/user-attachments/assets/7f0ad847-3f9a-48cc-bffa-1b9ed584bb59)

  ```
  liquibase rollbackCount 1
```
![liquibase u2](https://github.com/user-attachments/assets/5c7886a1-acaa-4dbe-9a37-8d633cfdb3ba)

## 3. **Rolling Back to Date**
  ```
liquibase history    
  ```
![liquibase h1](https://github.com/user-attachments/assets/b80dd1c4-fe3e-4e4c-bf80-ee9371ce777c)

```
  liquibase rollbackToDate 2024-09-13T04:38:00
```
![liquibase r3](https://github.com/user-attachments/assets/3bea279f-fbb9-4938-9297-74e962fe233c)


 ```
 liquibase history
```
By this we can see is rollback is successful or not

![liquibase h2](https://github.com/user-attachments/assets/6cb284b5-7008-4549-8609-6adae4721273)


