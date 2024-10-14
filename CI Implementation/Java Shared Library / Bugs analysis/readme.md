# Bug Analysis for Java - Shared Library 

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 14-10-2024  | Version 1  | Vinay Bansal    | 14-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Unit Testing](#-steps-to-conguration-unit-testing)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Shared Library for Bugs analysis in Java. Jenkins, as a popular automation server, supports a variety of build configurations. One of the critical aspects of Java CI checks is Bugs Analysis, which involves identifying, analyzing, and resolving bugs in the code to ensure software quality and reliability


---

## ⚙️ Pre-requisites

| **Requirement** | **Description**                                             |
|------------------|------------------------------------------------------------|
| **Jenkins**      | Ensure you have a Jenkins instance running.                |
| **Java**         | Required to run the built Java application.                |
| **Maven**        | Simplifies build management.                                |
| **SpotBugs**     | A static analysis tool that finds bugs in Java programs by analyzing bytecode. |


---

## 💥 Steps to Configuration to Bug Analysis
### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bug-analysis-shared`).
![image](https://github.com/user-attachments/assets/8ed91e15-f2a0-4db1-a9fa-5028e42168ac)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![image](https://github.com/user-attachments/assets/77b6469d-c1f6-48be-92c3-bb4a17aa4b7b)



### 4. 🚀 Create the repo for add src & vars file which will be using in pipeline script.
![image](https://github.com/user-attachments/assets/5687c4ec-44ec-4b87-9b88-1afa15d9691b)
![image](https://github.com/user-attachments/assets/9de4e8f9-addb-4805-ac35-18285c2dbe52)
![image](https://github.com/user-attachments/assets/f262f59a-d5d4-42c5-b1c9-fa79fb664835)
![image](https://github.com/user-attachments/assets/a7671642-cec1-46d9-ab49-e263ca98e44a)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Unit Testing analysis in the pipeline script ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/ec5a8f0d-aecb-42d7-aaeb-801a7e37d218)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/450e4202-1ac3-4c3c-bbd8-036bc170785a)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/6b9b1067-61e2-4a55-966c-00860639a822)
![image](https://github.com/user-attachments/assets/27632d82-b371-4a5a-8bb9-aeac3ba3faf2)


### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/68a24c88-e11d-429f-ba2b-f05906a92477) 



## 📛 Conclusion
We are using 'spotbugs' plugin in the current project. This shared library streamlines bug analysis in Java by leveraging powerful tool, offering reusable and modular components for detecting issues. It promotes consistency, reduces redundant code, and simplifies the integration of automated bug detection in CI/CD pipelines like Jenkins. By adopting this library, teams can enhance productivity and maintain high-quality code across multiple projects.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://tinyurl.com/66cr6xeh|SpotBugs Maven Plugin |
|https://tinyurl.com/56k8jfwp|(POC): Bug Analysis|
