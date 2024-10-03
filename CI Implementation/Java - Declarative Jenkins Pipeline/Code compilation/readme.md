
# Code compilation for Java - Declarative Jenkins Pipeline  


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 03-10-2024  | Version 1  | Vinay Bansal    | 03-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Code Compilation](#-steps-to-configuration-declarative-pipelines-for-code-compilation)
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


## 💥 Steps to Configuration Declarative pipelines for Code Compilation

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `code-compilation`).
![2](https://github.com/user-attachments/assets/2621f7b3-9ff8-42c6-b1f8-cb5e75387db5)

### 3. 🚀 Provide a description for the pipeline that performs code-compilation.
![3](https://github.com/user-attachments/assets/4cce2993-aeb1-469c-b97c-e3b644c3bf41)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for code-compilation in the pipeline configuration...>Click on Save to store the configuration.
![4](https://github.com/user-attachments/assets/86687d99-016f-4ec7-9132-addffb296fcd)



### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/edc403b0-0e63-4aca-8ce9-aa7ec6a5fe6c)

### 7.🚀 Click on Console Output to see the complete build.
![7](https://github.com/user-attachments/assets/e03d8595-d089-4a88-b812-6f1f75ca8d39)
![8](https://github.com/user-attachments/assets/154334b8-c48a-4fa4-a9b8-460e021c7682)




### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/6ea6223c-57c6-4888-83e9-eff267caf0f8)


## 📛 Conclusion

By following this guide, you have successfully configured Maven for code compilation in your Jenkins Declarative Pipeline without using Docker.Regularly compiling your code using Maven helps catch compilation issues early in the development process. Be sure to monitor the build results and integrate this compilation process into your CI/CD pipeline to ensure that code is built and tested thoroughly before deployment.

---

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/|Build a Java app with Maven |
|https://tinyurl.com/su8ennjz|(POC): code-compilation |
