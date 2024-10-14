# Dast- Declarative Jenkins Pipeline <img width="52" alt="image" src="https://github.com/user-attachments/assets/0c820c6d-f498-44f3-8d12-fc215c1268ea">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 14-10-2024  | Version 1  | Megha Tyagi     | 14-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Dast](#-steps-to-conguration-Dast)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline for DAST using OWASP ZAP, an open-source security tool. This Proof of Concept (PoC) will demonstrate how DAST can help detect and fix security issues to make web application more secure before it's launched.

---

## ⚙️ Pre-requisites

| **Prerequisite**       | **Description**                                                                                              |
|------------------------|--------------------------------------------------------------------------------------------------------------|
| **Python**             | Ensure Python (>= 3.6) is installed. Download it from [python.org](https://www.python.org/).                  |
| **OWASP ZAP**          | Install OWASP ZAP, which is available as a standalone package. You can also use [ZAP Docker Image](https://www.zaproxy.org/docs/docker/) for headless scans. |
| **Python ZAP Library** | Install the `python-owasp-zap-v2.4` library using `pip install python-owasp-zap-v2.4` for integration with Python. |
| **Target Application** | Attendance API to be tested must be accessible (either locally or remotely).                        |
| **Network Access**     | Ensure network access to the web app and allow ZAP's default API and scanning ports (usually 8090).           |


---

## 🔍 System Requirements

## Hardware System Requirements

| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

---

## 💥 Steps to Configuration Declarative pipelines for DAST
### Understand Declarative Pipeline syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Python%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md#understand-declarative-pipeline-syntax)

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `DAST`).
![Screenshot 2024-10-14 120016](https://github.com/user-attachments/assets/d23f9730-7dc5-4026-b062-f33d626ea564)


### 3. 🚀 Provide a description for the pipeline that performs DAST.
![Screenshot 2024-10-14 120056](https://github.com/user-attachments/assets/a6a2a85d-0528-4bbc-86f5-261f39048b8d)

### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![Screenshot 2024-10-14 182309](https://github.com/user-attachments/assets/f6f65210-a2ad-4651-8009-0a215ab07a3e)
![Screenshot 2024-10-14 182255](https://github.com/user-attachments/assets/ebfb8685-7d0b-41fe-8fec-e8f81676844f)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for DAST in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-14 182213](https://github.com/user-attachments/assets/40294155-2c4a-4a45-9044-9b5a7bc8cf5b)
<img width="958" alt="image" src="https://github.com/user-attachments/assets/49ebd02b-9061-4c9f-92ea-ac71e1515d7d">



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-14 182153](https://github.com/user-attachments/assets/4ed7c203-d400-4781-b13b-439f62cb8f1d)



### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-14 182054](https://github.com/user-attachments/assets/08855a06-f66d-4b4b-80ad-8f7bcdd09932)
![Screenshot 2024-10-14 182122](https://github.com/user-attachments/assets/fd465607-b191-431a-9d6e-b51318fe3e0a)
![Screenshot 2024-10-14 182237](https://github.com/user-attachments/assets/0ed6c623-ab34-4d94-bcf5-2fc5e7d92611)


### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-14 182034](https://github.com/user-attachments/assets/1f375a06-b006-47f6-a093-6fc94b193426)



## 📛 Conclusion
In this Proof of Concept (PoC), OWASP ZAP was used to perform Dynamic Application Security Testing (DAST) on the attendance-api application. The testing revealed several security issues, including the absence of a Content Security Policy (CSP) header. CSP helps protect the application against Cross-Site Scripting (XSS) and data injection attacks by allowing developers to specify which sources of content are safe to load.

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References

| Links | Descriptions|
|------|---------------------|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/DAST%20POC|(POC): DAST|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/DAST%20Doc|(DOC): DAST|





