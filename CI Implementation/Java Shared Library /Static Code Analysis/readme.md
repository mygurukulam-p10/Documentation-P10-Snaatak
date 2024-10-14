
# Static Code Analysis for Java - Shared Library 

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 14-10-2024  | Version 1  | Vinay Bansal    | 14-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Static Code Analysis](#-steps-to-conguration-static-code-analysis)
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


---

## 💥 Steps to Configuration to Static Code Analysis
### Understand Shared Library Syntax here[]


### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).


### 3. 🚀 Provide a description for the pipeline in detail what will perform.



### 4. 🚀 Create the repo for add src & vars file which will be using in pipeline script.



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code Analysis in the pipeline script ...> add repo link & credintial, file path.



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-


### 8.🚀 Click on Console Output to see the complete build.


### 9.🚀 Review the stages of the build process in the console output.



## 📛 Conclusion


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|

