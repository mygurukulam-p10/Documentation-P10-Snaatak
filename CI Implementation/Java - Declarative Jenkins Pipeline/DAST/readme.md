# Java - Declarative Jenkins Pipeline for DAST


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 05-10-2024  | Version 1  | Vinay Bansal    | 05-10-2024   |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for DAST](#-steps-to-configuration-declarative-pipelines-for-dast)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline for DAST using OWASP ZAP, an open-source security tool. This Proof of Concept (PoC) will demonstrate how DAST can help detect and fix security issues to make web application more secure before it's launched.


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **OWASP ZAP**:	Open source web application security scanner.

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

![image](https://github.com/user-attachments/assets/84d198c2-e6af-44e5-afb1-53dfe43110dc)


## 💥 Steps to Configuration Declarative pipelines for DAST

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `DAST`).
![2](https://github.com/user-attachments/assets/4ec96951-e3bb-4de2-a0ee-55350a9cb889)

### 3. 🚀 Provide a description for the pipeline that performs DAST.
![3](https://github.com/user-attachments/assets/de0685e5-2982-4653-8e94-c76dc8ca765a)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for DAST in the pipeline configuration...>Click on Save to store the configuration.
![4](https://github.com/user-attachments/assets/78e24a90-955f-490c-93ae-954555106842)



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/e22b3868-193c-4bca-ada6-3df5d1173088)

### 7.🚀 Click on Console Output to see the complete build.

![7](https://github.com/user-attachments/assets/3c637f46-42b9-451f-8242-682cb7e97dd2)
![8](https://github.com/user-attachments/assets/c2403f61-89bf-4a2b-87ec-d186f782616f)



### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/5e509411-232f-428f-bac8-f64e9b5622cb)


## 📛 Conclusion
In this Proof of Concept (PoC), OWASP ZAP was used to perform Dynamic Application Security Testing (DAST) on the salary-api application. The testing revealed several security issues, including the absence of a Content Security Policy (CSP) header. CSP helps protect the application against Cross-Site Scripting (XSS) and data injection attacks by allowing developers to specify which sources of content are safe to load.


##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/DAST/DAST%20DOC|(DOC): DAST|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/DAST/DAST%20POC|(POC): DAST|

