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

![image](https://github.com/user-attachments/assets/eb91843f-c210-491f-8ba6-6ed7a61a4961)

## 💥 Steps to Configuration Declarative pipelines for Bugs analysis

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bugs analysis`).
![2](https://github.com/user-attachments/assets/0162417c-5db4-4ff6-b875-dab4bb16beaa)

### 3. 🚀 Provide a description for the pipeline that performs Bugs analysis.
![3](https://github.com/user-attachments/assets/f8aa2ae9-0333-45b5-83b3-f40fb077dc3a)

### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM
![4](https://github.com/user-attachments/assets/8ffd51b8-115b-4a6e-a663-18b7b634d946)

### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![5](https://github.com/user-attachments/assets/11b9d8d0-4b3e-453a-b194-6fe15a70a385)

### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![7](https://github.com/user-attachments/assets/05b1b6a6-7cc7-4b9b-8923-9d7c1c7e1ed4)

### 8.🚀 Click on Console Output to see the complete build.
![8](https://github.com/user-attachments/assets/5043b246-6c7c-445e-9dc3-06ffda77b4cc)

![8 1](https://github.com/user-attachments/assets/df7346f7-8ad3-4630-b37b-dfa99be352d4)




### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/d0049f4c-a81d-4655-9e95-2f55e9c3c8bf)


## 📛 Conclusion

This POC shows that no plugin was found for the prefix 'spotbugs' in the current project and in the plugin groups. Integrating SpotBugs with Maven helps in detecting and analyzing code bugs and security vulnerabilities in the "salary-api" project. It provides easy-to-read reports (HTML/XML) that allow developers to identify, prioritize, and resolve issues early in the development process, improving both code quality and security.

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
