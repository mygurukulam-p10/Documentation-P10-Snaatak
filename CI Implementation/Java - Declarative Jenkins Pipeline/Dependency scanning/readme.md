
# Java - Declarative Jenkins Pipeline for Dependency scanning


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 05-10-2024  | Version 1  | Vinay Bansal    | 05-10-2024   |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Dependency scanning](#-steps-to-configuration-declarative-pipelines-for-dependency-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline for Dependency scanning. Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **OWASP Dependency-Check**:	A software composition analysis tool that identifies project dependencies and checks for known vulnerabilities.

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |


## 💥 Steps to Configuration Declarative pipelines for Dependency scanning

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency scanning`).
![2](https://github.com/user-attachments/assets/7449f5ee-c0f5-4afd-968d-127b7fbdce94)

### 3. 🚀 Provide a description for the pipeline that performs Dependency scanning.
![3](https://github.com/user-attachments/assets/81e1e782-18f7-45e2-a440-822cd273b048)

### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/f892b536-b19d-40ff-91c9-ba9e22083fe3)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for DAST in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/38cf7790-6d5e-4988-a151-7a162b9a4356)
![image](https://github.com/user-attachments/assets/981ccfc4-c80a-4fe0-8b2b-4a90a36d577c)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/0e85f208-00fb-498d-85e2-6bfeb11bfb3f)

### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/017b49c2-25f6-4e16-b664-49b374699200)





### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/ec8425b1-5e66-4dee-860c-f66f3e0d96a1)


## 📛 Conclusion
In conclusion, integrating OWASP Dependency-Check into your development process offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies. By regularly scanning and analyzing your project dependencies, you can stay ahead of known vulnerabilities, ensuring the overall security and reliability of your software applications

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://owasp.org/|OWASP Overview|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Dependency%20scanning%20POC|(POC): Dependency scanning|
