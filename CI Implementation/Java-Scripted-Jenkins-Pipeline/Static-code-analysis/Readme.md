
# Java - Scripted Jenkins Pipeline | Static code analysis 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Brij Singh     | 09-10-2024  | Version 1.2  | Brij Singh          | 15-10-2024     |      Shikha Tripathi / Aakash Tripathi	 /Shreya Jaiswal	         |  Pramod Rajput / Shashi              |  Ashwani |
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

[**Hardware Specifications**](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Static%20code%20analysis/readme.md)


![image](https://github.com/user-attachments/assets/5cf827f1-be38-4711-95ca-ffbe432b80cd)

## 💥 Steps to Configuration Scripted Pipeline for Static Code Analysis
#

### 1. 🚀 Open your Jenkins Dashboard.
 ![image](https://github.com/user-attachments/assets/6d4e90fc-179f-4a0c-b6bf-554a9227fc5d)


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static-Code-Analysis`).

![image](https://github.com/user-attachments/assets/9632140f-f2b9-4c7d-8c44-dc666fb721e9)


### 3. 🚀 Provide a description for the pipeline that performs Static-Code-Analysis.
![image](https://github.com/user-attachments/assets/7af9d84d-6a18-4787-a3bf-60c591ada1f3)


### 4. 🚀 Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/17f43a3e-8d3f-4603-96a2-9999cc998697)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/b87d23a2-6cfc-4671-b49a-f074bab567dd)


### 6. 🚀 Then Click on build to run the pipeline to perform
![image](https://github.com/user-attachments/assets/a0a5fd3d-4fd5-43e0-aa16-218a1c1cd6ab)


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/fdaf2b03-05e7-4e06-af5a-2fd6df1faf0d)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/6e52b87c-1e92-4bc8-927f-60848007654a)

![image](https://github.com/user-attachments/assets/daced57f-d1c7-433b-bc11-58f3e553a410)

![image](https://github.com/user-attachments/assets/2e4255e6-337e-4d7d-b13b-f7fe5380ae07)

![image](https://github.com/user-attachments/assets/badc9c19-54a4-44fb-835b-a34261ab2ba6)




### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/f9209c2c-6c6d-4cb9-9798-dc61c03a7ca6)



## 📛 Conclusion

We run Checkstyle and found 88 code violations. This means there are parts of the code that don't follow our coding standards. These issues can make the code harder to read and maintain.


##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Brij Singh | Brij.singh.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://maven.apache.org/plugins/maven-checkstyle-plugin/|Apache Maven Checkstyle Plugin|
|https://tinyurl.com/mrxmx9wy|(POC): Static Code Analysis|
