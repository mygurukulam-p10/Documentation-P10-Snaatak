# Java - Declarative Jenkins Pipeline for Unit Testing 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 04-10-2024  | Version 1  | Vinay Bansal    | 04-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Unit Testing](#-steps-to-configuration-declarative-pipelines-for-unit-testing)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Java Unit Testing. Jenkins, as a popular automation server, supports a variety of build configurations.


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **Spotbug**: A static analysis tool that finds bugs in Java programs by analyzing bytecode.

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |


## 💥 Steps to Configuration Declarative pipelines for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Unit Testing`).
![2](https://github.com/user-attachments/assets/286ef69d-72f5-4144-aa79-70be1ec924ac)

### 3. 🚀 Provide a description for the pipeline that performs Unit Testing.
![3](https://github.com/user-attachments/assets/c8d597f6-4654-4587-b99f-663ca3ec7764)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Unit Testing in the pipeline configuration...>Click on Save to store the configuration.
![4](https://github.com/user-attachments/assets/ca805260-2124-4b67-b0d4-d272942da7f2)



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/93d40d3a-011b-46e1-ae83-9e346441c86e)

### 7.🚀 Click on Console Output to see the complete build.
![7](https://github.com/user-attachments/assets/10f384c3-eea1-422b-8bdd-fe36e196cf0d)




### 9.🚀 Review the stages of the build process in the console output.

![9](https://github.com/user-attachments/assets/d93b8dfd-5708-414b-a966-f46d706986a3)

## 📛 Conclusion

By incorporating unit tests into the development lifecycle, you can ensure code reliability, early bug detection, and maintainability. Tools like Maven and JUnit, along with best practices such as isolating tests and automating the testing process, significantly improve software quality. The continuous integration setup automates the testing process, ensuring that any new changes do not break existing functionality.
##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://www.browserstack.com/guide/unit-testing-java|Unit Testing in Java|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Unit%20Testing/POC|(POC): Unit Testing|
