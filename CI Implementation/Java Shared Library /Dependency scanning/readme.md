Dependency Scanning for Java - Shared Library 

![image](https://github.com/user-attachments/assets/3a9fce15-13ae-46e2-bd1a-e2d2d9215688)

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|-------------|------------|-----------------|----------------|------------|-----------------|----------------|
| Vinay Bansal | 14-10-2024  | Version 1  | Vinay Bansal    | 17-10-2024     |Shikha Tripathi||

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration to Dependency Scanning](#-steps-to-configuration-to-dependency-scanning)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Shared Library for Dependency Scanning in Java. Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on


---

## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **OWASP Dependency-Check**: A software composition analysis tool that identifies project dependencies and checks for known vulnerabilities.

   
## 🔍 System Requirements [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Static%20code%20analysis/readme.md#-system-requirements)


---

## 💥 Steps to Configuration to Static Code Analysis
### Understand Shared Library Syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/CI%20Implementation/Java%20Shared%20Library%20/%20Bugs%20analysis#understand-shared-library-syntax)

### OWASP Dependency-Check plugin [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Dependency%20scanning/readme.md#to-enable-the-owasp-dependency-check-plugin-in-your-maven-project-add-the-following-configuration-to-your-pomxml-file-ensure-this-configuration-is-placed-within-the--section)
### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).
![image](https://github.com/user-attachments/assets/2ca0a79c-2823-493e-ad6b-58b6b720fde8)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![image](https://github.com/user-attachments/assets/22a38ab6-398b-4435-b955-18e5efaaddf2)



### 4. 🚀 Create the repo for add vars file which will be using in pipeline script.
![image](https://github.com/user-attachments/assets/d3d4c53f-0ab9-4834-89a1-02f2709c9be6)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Dependency Scanning in the pipeline script ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/6f462105-cb02-4dc8-89c3-2d817c90fef8)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/8abf8183-259c-4654-a858-7eb648c77a32)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/ac34383b-67f8-40ac-b56e-f504eca7998d)
![image](https://github.com/user-attachments/assets/b75a56c7-fbd8-48d5-a1f9-3be60580fcdb)

### 9.🚀 Verify Report
![image](https://github.com/user-attachments/assets/9e5e2f60-fa8f-4971-bc42-886a2270e113)


### 10.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/ea6009b2-5689-4c2c-badb-44247609087d)



## 📛 Conclusion
We are using 'OWASP Dependency-Check' plugin in the current project. This shared library streamlines Dependency Check in Java offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://owasp.org/|OWASP Overview|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Dependency%20scanning%20POC|(POC): Dependency scanning|
