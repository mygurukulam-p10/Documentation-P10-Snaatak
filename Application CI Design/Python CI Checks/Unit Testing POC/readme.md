# Proof of Concept (POC) for Unit Testing
![python](https://github.com/user-attachments/assets/b67f3abf-d7e8-4022-8f39-9c534df7bd53)



  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 23-09-24 | version 1 | Vinay Bansal | 24-09-24 |

## Purpose
The purpose of this document is to provide a completed guide to step Unit Testing.
  
  ## Table of Contents
+ [Introduction](#Introduction)
+ [Pre-requisites](#pre-requisites)
+ [ System Requirements](#System-Requirements)
+ [Build-Time Dependency](#build-time-dependency)
+ [Run Time Dependency](#run-time-dependency)
+ [Step-by-step Installation](#step-by-step-installation)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [ References](#references)

## ⚙️ Pre-requisites

- Ensure you have Python 3.11 installed on your machine. 
- Package Manager:pip
- Version Control System:

## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                    |
| Disk                     |10 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠️ Build-Time Dependency

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

##  🌐Important Ports
| 🔌 Inbound Traffic | Description        |
| --------------- | ------------------ |
| 5432            | Used by Postgres  |

## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
https://github.com/OT-MICROSERVICES/attendance-api.git
```

# Step 2: For Unit Tresting

## First Install
![u1](https://github.com/user-attachments/assets/7e8ac84c-d519-49a8-9a22-b298c2d064a0)

```
pip install pytest
```


![ue1](https://github.com/user-attachments/assets/2f21f68c-1d57-4680-9824-f11cdf73dc77)

Ensure that psycopg2 is installed correctly. If you’re using psycopg2, it should work without any issues. You can install it via pip:
```
pip install psycopg2
```
![ue2](https://github.com/user-attachments/assets/1cc9c6dd-63ab-466a-8b67-de76d6bea345)

Ensure that you’re importing the extras module properly in your code. The import statement should look like this:
```
import psycopg2
from psycopg2 import extras
```

![ue1cp](https://github.com/user-attachments/assets/6d686ca4-4223-476d-bbe9-b7b691dc2cc5)
you need to install the pytest-mock library, which provides the mocker fixture. You can do this using pip:
```
pip install pytest-mock
```
![ue1rou](https://github.com/user-attachments/assets/6427ef04-2464-4aee-a3b6-0d62e463b28e)

router
Install Flask: If Flask is not installed, you can install it using pip. Run the following command in your terminal:
```
pip install Flask
```
Install Flask-Caching: Install the flask_caching package using pip:
```
pip install Flask-Caching
```
![ue1u](https://github.com/user-attachments/assets/361d64bc-fc4d-460f-93e1-2c08d2e050ef)

utils/tests/test_json_encoder.py
Install Peewee: If you haven't installed the peewee library, you can do so using pip:
```
pip install peewee
```

utils/tests/test_log_encoder.py
Install the Module: If you haven't installed pythonjsonlogger, you can do so using pip:
```
pip install python-json-logger
```

utils/tests/test_validator.py
Install Voluptuous: If you haven’t installed voluptuous, you can do so using pip:
```
pip install voluptuous
```
![usuccess](https://github.com/user-attachments/assets/157685e6-011f-4ea7-ae3a-eba410dfbfa7)





# Conclusion
Using `pytest` as your testing framework significantly enhances your testing strategy by providing a flexible and easy-to-use interface. Its features promote good testing practices, allowing for better code quality and maintainability. Embracing `pytest` in your development process, along with effective CI practices, ensures a robust and reliable codebase.

## Contact Information

| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## References
For further reading and resources on GitOps, check out the following:

| Links | Descriptions|
|------|---------------------|
|Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Python%20CI%20Checks/Unit%20Testing%20Doc/readme.md|
