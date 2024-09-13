# Employee Application POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 10-09-24    | version 1  | Megha Tyagi     | 10-09-24       |

## Purpose
The purpose of this POC is to demonstrate the functionality and integration of the ReactJS-based frontend application as the main UI for the OT-Microservices stack. This POC will validate the application's cross-platform compatibility, confirm its ability to operate with only JavaScript runtime modules, and verify the seamless execution of web page operations using the ReactJS framework. Additionally, the POC aims to test the integration and reliability of test cases for ensuring proper application functionality.

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
8. [Application Build](#application-build)


## Architecture


![Employee_API Architecture drawio](https://github.com/user-attachments/assets/baecdfb0-8c23-4c02-8803-d0bfee23a8e1)

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

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
| ScyllaDB       | 6.1.1   |ScyllaDB is a NoSQL database being utilized as the primary database in the employee application                                      |
| Redis          | 6.0.16  |Redis is an in-memory data structure store used for caching to enhance the performance and response time of the employee application.|


## Build Dependency
| Name           | Version    | Description        |
| -------------- | ---------- | ------------------ |
| NVM 14        |  4.17.1    | These represent the data migration scripts or processes that ensure the data in ScyllaDB is up to date.Migrations are usually used when the database schema or structure changes.   |
| Jq       | 1.6   | jq is likely being used to parse or manipulate JSON data related to the migration process. This could involve extracting configuration values, database connection strings, or other parameters that are stored in a JSON format.| 

## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 6379            | Used by Redis      |
| 9042            | Used by ScyllaDB   |

```
sudo apt install nodejs npm
```
<img width="959" alt="npm install" src="https://github.com/user-attachments/assets/a3eb0f6d-ebf3-4343-9d67-24c8538b57bf">

