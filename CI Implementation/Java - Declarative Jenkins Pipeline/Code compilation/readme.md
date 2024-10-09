
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
4. Knowledge of your Tool's [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/code%20compilation%20doc).


## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

![image](https://github.com/user-attachments/assets/d885b5fa-d515-4c80-91c5-74c6d2fb00e8)


## 💥 Steps to Configuration Declarative pipelines for Code Compilation
### Understand Declarative Pipeline syntax
| Component                    | Description                                                                                   |
|------------------------------|-----------------------------------------------------------------------------------------------|
| **pipeline { ... }**        | Defines the entire pipeline structure.                                                        |
| **agent any:**               | Specifies that the pipeline can run on any available Jenkins agent (worker node).           |
| **stages { ... }**          | Contains all the stages of the pipeline. Each stage represents a logical part of the build process. |
| **stage('Clone Repository') { ... }** | Defines a stage named "Clone Repository." Typically represents a specific task.            |
| **steps { ... }**           | Defines the individual steps to be executed within the stage.                                |
| **post { ... }**            | Contains actions executed after all stages have finished, regardless of the build's outcome. |
| **success { ... }**         | Actions executed if the pipeline completes successfully (i.e., all stages are successful).    |
| **failure { ... }**         | Actions executed if the pipeline fails at any stage.                                         |


### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `code-compilation`).
![2](https://github.com/user-attachments/assets/2621f7b3-9ff8-42c6-b1f8-cb5e75387db5)

### 3. 🚀 Provide a description for the pipeline that performs code-compilation.
![3](https://github.com/user-attachments/assets/4cce2993-aeb1-469c-b97c-e3b644c3bf41)

### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM
![4](https://github.com/user-attachments/assets/8eba668d-9025-42d3-8b82-fa9fa8785557)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![5](https://github.com/user-attachments/assets/9b41936a-f3fc-4d2d-8228-828a66428902)

### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![7](https://github.com/user-attachments/assets/87b0bd65-387d-472b-a082-c029d105275b)

### 8.🚀 Click on Console Output to see the complete build.
![8](https://github.com/user-attachments/assets/3387888b-ed63-4032-87fd-0a35697c612f)

![8](https://github.com/user-attachments/assets/154334b8-c48a-4fa4-a9b8-460e021c7682)




### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/9c85a377-5c68-4cb3-b441-e35bc71d61e2)


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
