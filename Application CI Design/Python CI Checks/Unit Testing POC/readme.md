# Proof of Concept (POC) for Unit Testing for Python
![image](https://github.com/user-attachments/assets/fa7ac02a-6531-44d2-8302-9e2797eb0277)



  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 23-09-24 | version 1 | Vinay Bansal | 24-09-24 |

## Purpose
The purpose of this document is to provide a completed guide to step Unit Testing.
  
  ## Table of Contents
- [Introduction](#introduction)
- [⚙️ Pre-Requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🛠️ Build-Time Dependency](#-build-time-dependency)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🌐 Important Ports](#-important-ports)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📧 Contact Information ](#-contact-information )
- [📚 References](#-references )

## Introduction
This document will guide you through setting up a Python project, including the necessary prerequisites, creating a basic project structure, and adding unit testing capabilities using pytest

## ⚙ Pre-requisites

- Ensure you have Python 3.11 installed on your machine. 
- Package Manager:pip
- Version Control System:

## 🖥 System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 2 GB                    |
| Disk                     |10 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠 Build-Time Dependency

| 🛠️ Name | 📦 Version | 📄 Description |
|---------|------------|----------------|
| **pytest** | 7.4.0  | Needed for running tests. |
|**poetry**| 1.9.0 | managing dependencies in a more structured way.|
|**Pip**  | 3.11    | Used for installing Python packages.|


## 🚀 Run-Time Dependency

| 🚀 Name | 📦 Version | 📄 Description          |
|---------|------------|--------------------------|
| **Flask** |  6.0.0      | Frameworks for building web applications. |
|**psycopg2**| 14 | Libraries for database interaction.|

## 🌐 Important Ports
| 🔌 Inbound Traffic | Description        |
| --------------- | ------------------ |
| 5432            | Used by Postgres  |


## 🏗 Architecture
<img width="582" alt="image" src="https://github.com/user-attachments/assets/7c205d87-f1aa-48f5-9240-3151d158676d">


## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
###  Step 1: Clone the Git Repository
```
https://github.com/OT-MICROSERVICES/attendance-api.git
```
### Step 2: Change Directory
Change Directory to where your code is
```
cd attendance-api
```

## First Install

# Step 3: For Unit Tresting

## First Install
running pip install pytest installs the pytest library, enabling you to write and run tests for your Python code effectively.
```
pip install pytest
```
![u1](https://github.com/user-attachments/assets/7e8ac84c-d519-49a8-9a22-b298c2d064a0)




<details>
  <summary>Error in PostgreSQL</summary>
  <img width="758" alt="image" src="https://github.com/user-attachments/assets/8550edf4-6cd5-4e34-95a0-506454895fb0">

- enabling your Python applications to communicate with PostgreSQL databases.
```
pip install psycopg2
```
</details>

<details>
  <summary>Error in PostgreSQL</summary>
  
![ue2](https://github.com/user-attachments/assets/1cc9c6dd-63ab-466a-8b67-de76d6bea345)

- Using these imports, you can easily connect to a PostgreSQL database and utilize advanced features provided by psycopg2.
```
import psycopg2
from psycopg2 import extras
```
</details>

 <details> 
 <summary>Error in PostgreSQL</summary>
   
![ue1cp](https://github.com/user-attachments/assets/6d686ca4-4223-476d-bbe9-b7b691dc2cc5)
-  running pip install pytest-mock installs the pytest-mock library, allowing you to effectively use mocking techniques in your pytest tests to isolate and test specific functionalities without relying on external dependencies.
```
pip install pytest-mock
```
 </details>


<details>
      <summary>Error in Router</summary>
  
![ue1rou](https://github.com/user-attachments/assets/6427ef04-2464-4aee-a3b6-0d62e463b28e)

router
- running pip install Flask installs the Flask framework, allowing you to develop web applications in Python efficiently.
```
pip install Flask
```
- running pip install Flask-Caching installs the Flask-Caching extension, enabling you to implement caching in your Flask applications to enhance performance and reduce server load.
```
pip install Flask-Caching
```
</details>


<details>
  <summary>Error in Utils</summary>
  
![ue1u](https://github.com/user-attachments/assets/361d64bc-fc4d-460f-93e1-2c08d2e050ef)

utils/tests/test_json_encoder.py
- running pip install peewee installs the Peewee library, enabling you to use an ORM(stands for Object-Relational Mapping. It is a programming technique that allows developers to interact with a database using object-oriented programming languages.) for database interactions in your Python applications.
```
pip install peewee
```

utils/tests/test_log_encoder.py
running pip install python-json-logger installs the python-json-logger library, enabling you to format log messages as JSON, which is useful for structured logging in applications.
```
pip install python-json-logger
```

utils/tests/test_validator.py
- running pip install voluptuous installs the Voluptuous library, enabling you to validate Python data structures against defined schemas efficiently.
```
pip install voluptuous
```
</details>


## To check how many test cases have passed (or failed) when using pytest
this command is a common way to run unit tests in Python projects, leveraging the capabilities of the pytest framework.
```
python3 -m pytest
```
![usuccess](https://github.com/user-attachments/assets/157685e6-011f-4ea7-ae3a-eba410dfbfa7)
- Running python3 -m pytest and seeing a success message means that all the tests in your test suite were collected and passed successfully. Specifically, pytest will exit with a code 0, indicating that there were no test failures, errors, or interruptions


## 📧 Contact Information

| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## 📚 References
For further reading and resources on GitOps, check out the following:

| Links | Descriptions|
|------|---------------------|
|Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Python%20CI%20Checks/Unit%20Testing%20Doc/readme.md|
