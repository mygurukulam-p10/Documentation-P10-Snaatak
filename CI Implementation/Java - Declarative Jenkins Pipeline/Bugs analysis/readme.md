# Java - Declarative Jenkins Pipeline for Bugs analysis  


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 04-10-2024  | Version 1  | Vinay Bansal    | 04-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Bugs analysis](#-steps-to-configuration-declarative-pipelines-for-bugs-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Java Bugs analysis. Jenkins, as a popular automation server, supports a variety of build configurations.


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


## 💥 Steps to Configuration Declarative pipelines for Bugs analysis

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bugs analysis`).

### 3. 🚀 Provide a description for the pipeline that performs Bugs analysis.

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Bugs analysis in the pipeline configuration...>Click on Save to store the configuration.



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-

### 7.🚀 Click on Console Output to see the complete build.




### 9.🚀 Review the stages of the build process in the console output.


## 📛 Conclusion

This POC shows how integrating SpotBugs with Maven helps in detecting and analyzing code bugs and security vulnerabilities in the "salary-api" project. It provides easy-to-read reports (HTML/XML) that allow developers to identify, prioritize, and resolve issues early in the development process, improving both code quality and security.

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://tinyurl.com/66cr6xeh|SpotBugs Maven Plugin |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Application%20CI%20Design/Java%20CI%20checks/Bugs%20analysis/POC/Poc.md|(POC): Bug Analysis|
