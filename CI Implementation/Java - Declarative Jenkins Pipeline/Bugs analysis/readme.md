# Java - Declarative Jenkins Pipeline for Bugs analysis  


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 04-10-2024  | Version 1  | Vinay Bansal    | 11-10-2024     |

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

### 4. 🚀 Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/7a101075-f65a-44ef-a72c-150e067ed2da)

### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/c9ed5684-1744-40a7-9094-f8788083eb8b)
![image](https://github.com/user-attachments/assets/4b6b0573-10aa-4542-ac2b-729986148b54)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/889976fb-0b38-49f5-bdc8-454a4af01d42)

### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/41c4ccad-d723-43e3-b742-8e53d824fcca)
![image](https://github.com/user-attachments/assets/47eefaeb-24f7-4502-892b-6f92c95eab3d)




### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/d9a97542-1e4e-40ab-b6a1-595ab54ed07c)


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
