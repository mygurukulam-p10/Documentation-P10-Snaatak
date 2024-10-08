# Java - Declarative Jenkins Pipeline for Unit Testing 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 04-10-2024  | Version 1  | Vinay Bansal    | 04-10-2024   |

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
4. **JUnit**: A necessary library for executing the unit tests.

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

![image](https://github.com/user-attachments/assets/dc89a11e-c25f-4ad5-8221-9f9c7b442682)

## 💥 Steps to Configuration Declarative pipelines for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Unit Testing`).
![2](https://github.com/user-attachments/assets/286ef69d-72f5-4144-aa79-70be1ec924ac)

### 3. 🚀 Provide a description for the pipeline that performs Unit Testing.
![3](https://github.com/user-attachments/assets/c8d597f6-4654-4587-b99f-663ca3ec7764)

### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM
![5](https://github.com/user-attachments/assets/52a69592-a185-485c-9700-0aabc193716a)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![4](https://github.com/user-attachments/assets/8038c415-ffe1-40a2-b54a-cd9e9cd4042f)

### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![7](https://github.com/user-attachments/assets/1f4c672e-173c-4490-a953-7a8ff68ccb9a)

### 8.🚀 Click on Console Output to see the complete build.
![8](https://github.com/user-attachments/assets/1ef0c681-1c75-420e-9b0a-d0db2ef09e2a)
![8 1](https://github.com/user-attachments/assets/5a28307f-7c64-4444-aade-ef8dcab1902c)




### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/a5dabe92-d39f-4c8b-9d22-3063cbbddbd3)


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
