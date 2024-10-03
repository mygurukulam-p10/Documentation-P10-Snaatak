# Java - Declarative Jenkins Pipeline for Static code analysis


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 03-10-2024  | Version 1  | Vinay Bansal    | 03-10-2024     |

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
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Java code compilation. Jenkins, as a popular automation server, supports a variety of build configurations.


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 4 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |


## 💥 Steps to Configuration Declarative pipelines for Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
![1](https://github.com/user-attachments/assets/5bc5a337-706e-43aa-9283-69c8c0858560)

### 3. 🚀 Provide a description for the pipeline that performs Static Code Analysis.
![2](https://github.com/user-attachments/assets/de6eac31-cd05-4848-9bf1-ac63960402a4)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code Analysis in the pipeline configuration...>Click on Save to store the configuration.
![3](https://github.com/user-attachments/assets/71859180-adea-46d6-b605-3c64fed6a074)



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/c7f3dfaa-f13f-46b4-9cd6-931165099045)

### 7.🚀 Click on Console Output to see the complete build.
![4](https://github.com/user-attachments/assets/736614e1-c66f-4454-bc62-02750024f614)

![5](https://github.com/user-attachments/assets/66e44902-daf0-4569-b349-de9816bb528b)




### 9.🚀 Review the stages of the build process in the console output.
![7](https://github.com/user-attachments/assets/a1174bde-bc70-4d9c-a83d-1fa7b46eab1f)


## 📛 Conclusion

We ran Checkstyle and found 88 code violations. This means there are parts of the code that don't follow our coding standards. These issues can make the code harder to read and maintain.


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
