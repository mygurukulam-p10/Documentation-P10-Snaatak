# Java - Declarative Jenkins Pipeline for Static Code Analysis


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|-------------|------------|-----------------|----------------|----|-----|-----|
| Vinay Bansal | 03-10-2024  | Version 1  | Vinay Bansal    | 03-10-2024     |Shikha Tripathi|	Pramod Rajput|	Ashwani

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Static code analysis](#-steps-to-configuration-declarative-pipelines-for-static-code-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Java Static code analysis. Jenkins, as a popular automation server, supports a variety of build configurations.Static code analysis is the process of examining source code without executing it to identify potential issues, improve quality.


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **Tools for Static Code Analysis** [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Static%20Code%20Analysis%20Doc).

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

![image](https://github.com/user-attachments/assets/5cf827f1-be38-4711-95ca-ffbe432b80cd)

## 💥 Steps to Configuration Declarative pipelines for Static Code Analysis
### Understand Declarative Pipeline syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md#understand-declarative-pipeline-syntax)

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
![1](https://github.com/user-attachments/assets/5bc5a337-706e-43aa-9283-69c8c0858560)

### 3. 🚀 Provide a description for the pipeline that performs Static Code Analysis.
![2](https://github.com/user-attachments/assets/de6eac31-cd05-4848-9bf1-ac63960402a4)

### 4. 🚀 Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![4](https://github.com/user-attachments/assets/49a6c368-0382-4da0-af4b-ad9d1822f13f)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![5](https://github.com/user-attachments/assets/19409866-550d-47bf-bb77-df8567e19701)

### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/f368b5ae-5ca5-4f05-baec-9732771d5168)

### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/520ffc07-2e69-4d07-be17-ef365ecad184)
![image](https://github.com/user-attachments/assets/ade662d5-fd89-4cb2-9ba9-b845bfb66c4b)




### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/3f1356c7-94ba-4381-b8bd-1b3756b00ed0)


## 📛 Conclusion

We run Checkstyle and found 88 code violations. This means there are parts of the code that don't follow our coding standards. These issues can make the code harder to read and maintain.


##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://maven.apache.org/plugins/maven-checkstyle-plugin/|Apache Maven Checkstyle Plugin|
|https://tinyurl.com/mrxmx9wy|(POC): Static Code Analysis|
