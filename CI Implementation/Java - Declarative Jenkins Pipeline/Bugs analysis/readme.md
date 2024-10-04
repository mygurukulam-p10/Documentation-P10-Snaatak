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
![2](https://github.com/user-attachments/assets/0162417c-5db4-4ff6-b875-dab4bb16beaa)

### 3. 🚀 Provide a description for the pipeline that performs Bugs analysis.
![3](https://github.com/user-attachments/assets/f8aa2ae9-0333-45b5-83b3-f40fb077dc3a)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Bugs analysis in the pipeline configuration...>Click on Save to store the configuration.
![4](https://github.com/user-attachments/assets/42e9b6ad-3dc4-4926-ab76-ca077f9fadcf)



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/7836be27-234a-4810-97df-6e132460d06b)

### 7.🚀 Click on Console Output to see the complete build.
![7](https://github.com/user-attachments/assets/6230dc67-c07d-4fb2-ab04-d81e77d5159a)

![8](https://github.com/user-attachments/assets/2f298c39-fb71-49fa-ac12-95805e05fd86)




### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/25f61bf1-0998-4161-9922-27f9837c1fa4)


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
|https://tinyurl.com/56k8jfwp|(POC): Bug Analysis|
