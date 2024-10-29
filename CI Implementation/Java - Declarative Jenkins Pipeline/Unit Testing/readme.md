# Java - Declarative Jenkins Pipeline for Unit Testing 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|-------------|------------|-----------------|----------------|-|-|-|
| Vinay Bansal | 04-10-2024  | Version 1  | Vinay Bansal    | 11-10-2024   |Shikha Tripathi|Shashi|Ashwani|

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
### Understand Declarative Pipeline syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md#understand-declarative-pipeline-syntax)

### Add the JUnit Dependency to pom.xml
```
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
    <scope>test</scope>
</dependency>
```

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Unit Testing`).
![2](https://github.com/user-attachments/assets/286ef69d-72f5-4144-aa79-70be1ec924ac)

### 3. 🚀 Provide a description for the pipeline that performs Unit Testing.
![3](https://github.com/user-attachments/assets/c8d597f6-4654-4587-b99f-663ca3ec7764)

### 4. 🚀 Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/ba76a525-7fd6-44eb-9904-c0ce2ac18b6f)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/3868e87f-a93a-4586-908c-e662b18443a5)
![image](https://github.com/user-attachments/assets/a7576d77-b40f-4c1d-8758-261dc96c7ef8)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/49dd67c7-9d21-4d12-ac5f-c7529c30efef)

### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/680a1f07-9f61-4c17-bc53-eb75f529bc75)

![image](https://github.com/user-attachments/assets/023cfeab-90b0-43ce-a5e3-569857232eb3)




### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/21cdfce3-4cb3-4544-99fa-cf88ee48ebd0)


## 📛 Conclusion

We run the code using command mvn test. By using unit tests into the development lifecycle, you can ensure code reliability, early bug detection, and maintainability. Tools like Maven and JUnit, along with best practices such as isolating tests and automating the testing process, significantly improve software quality. The continuous integration setup automates the testing process, ensuring that any new changes do not break existing functionality.
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
