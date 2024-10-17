# Java - Declarative Jenkins Pipeline for DAST
![image](https://github.com/user-attachments/assets/594c9f0e-a211-4ae2-aa60-f16ab32affbc)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 05-10-2024  | Version 1  | Vinay Bansal    | 15-10-2024   |

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
### Understand Declarative Pipeline syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md#understand-declarative-pipeline-syntax)

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `DAST`).
![2](https://github.com/user-attachments/assets/4ec96951-e3bb-4de2-a0ee-55350a9cb889)

### 3. 🚀 Provide a description for the pipeline that performs DAST.
![3](https://github.com/user-attachments/assets/de0685e5-2982-4653-8e94-c76dc8ca765a)

### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/305882ab-ea26-4eb0-9c44-f3b0b7c47d4b)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for DAST in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/2d74152d-c7d2-4b8c-9774-40a25141f36c)




### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/bedf8dfd-a2c1-419e-a6c4-94657f19d23a)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/eeafc50c-0c03-4586-8fa1-dab035a97d91)
![image](https://github.com/user-attachments/assets/a29ac895-a618-4549-9d6c-eb07b1777886)

### 9.🚀 Verify Report.
![image](https://github.com/user-attachments/assets/9b2a454d-b4cc-45ac-af77-1d1ea69e2a8a)
![image](https://github.com/user-attachments/assets/a4799f9c-1460-4e72-8830-81e1100c8509)



### 10.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/5d678f5d-d0dd-4509-9ce4-275ff126b27d)


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

