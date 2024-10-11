
# Java - Scripted Jenkins Pipeline | Dependency scanning


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Brij Singh | 10-10-2024  | Version 1  | Brij Singh   | 10-10-2024   |

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
This document outlines how to set up a Scripted Jenkins Pipeline  for Dependency scanning. Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on


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


## 💥 Steps to Configuration Scripted Jenkins Pipeline for Dependency scanning

### 1. 🚀 Open your Jenkins Dashboard.

![image](https://github.com/user-attachments/assets/ccfbe1a0-dce5-4df6-a265-7268b26d8c80)


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency scanning`).

![image](https://github.com/user-attachments/assets/f1db9473-3f34-40a1-9246-fc699df19756)


### 3. 🚀 Provide a description for the pipeline that performs Dependency scanning.
![image](https://github.com/user-attachments/assets/5180b764-2ac1-430f-aa97-0c010d600ade)


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Dependency scanning in the pipeline configuration...>Click on Save to store the configuration.
![image](https://github.com/user-attachments/assets/3bbca678-5495-49b5-8937-5dcc5aca32ac)





### 5. 🚀 Then Click on build to run the pipeline to perform
![image](https://github.com/user-attachments/assets/dbd7caaf-b587-454d-878f-6a65c300dc18)


### 6.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/368e3144-740d-47d4-94f8-09df9bc63158)



### 7.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/2d644f62-4ace-44cb-8e1f-466c4bd18958)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/557263d6-6c1f-451c-9804-1c6cdc09e59a)

![image](https://github.com/user-attachments/assets/e00fa847-dedc-45d2-9359-21d2d28a2b22)

![image](https://github.com/user-attachments/assets/2deb4d93-bb4f-4c0c-9a37-5a561df60ea1)

### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/1d1af06c-1be5-4656-af99-c4e2a0d9c256)



## 📛 Conclusion
In conclusion, integrating OWASP Dependency-Check into your development process offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies. By regularly scanning and analyzing your project dependencies, you can stay ahead of known vulnerabilities, ensuring the overall security and reliability of your software applications

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Brij Singh | Brij.Singh.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|---------------|---------------------|
|  OWASP Overview |[link](https://owasp.org/) ||
| Dependency scanning |[link](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Dependency%20scanning%20POC) |

