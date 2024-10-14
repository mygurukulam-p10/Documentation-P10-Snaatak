
# Static Code Analysis for Java - Shared Library 

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 14-10-2024  | Version 1  | Vinay Bansal    | 14-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration to Static Code Analysis](#-steps-to-configuration-to-static-code-analysis)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Shared Library for Bugs analysis in Java. Jenkins, as a popular automation server, supports a variety of build configurations. Static code analysis is the process of examining source code without executing it to identify potential issues, improve quality.


---

## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **Tools for Static Code Analysis** [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Static%20Code%20Analysis%20Doc).

## 🔍 System Requirements [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Static%20code%20analysis/readme.md#-system-requirements)


---

## 💥 Steps to Configuration to Static Code Analysis
### Understand Shared Library Syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/CI%20Implementation/Java%20Shared%20Library%20/%20Bugs%20analysis#understand-shared-library-syntax)


### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
![image](https://github.com/user-attachments/assets/00daf044-f056-4c4c-8464-0d62828ea964)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![image](https://github.com/user-attachments/assets/abb8011a-de5d-41ec-a64c-467f3baa768f)



### 4. 🚀 Create the repo for add src & vars file which will be using in pipeline script.
![image](https://github.com/user-attachments/assets/295fd8fb-899b-4faa-9d23-59770b1aff34)
![image](https://github.com/user-attachments/assets/581b80b8-317e-42bc-8aac-d4a371e36c4a)
![image](https://github.com/user-attachments/assets/100a6dbb-73d4-4328-b200-e66f214f5871)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code Analysis in the pipeline script ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/fa17d726-f6c4-44c1-afba-58b8fd119fa6)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/94235b45-db66-400e-9e1e-df60b74b37ab)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/02e0eda4-926a-4604-9f07-cff01185f2ad)
![image](https://github.com/user-attachments/assets/bc844fd4-5d29-4c18-8d6b-e9e165124407)


### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/f338ae55-f6a7-489b-bf28-d7a7d01f2a68)



## 📛 Conclusion
We run Checkstyle command and found 88 code violations. This means there are parts of the code that don't follow our coding standards. These issues can make the code harder to read and maintain.

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://maven.apache.org/plugins/maven-checkstyle-plugin/|Apache Maven Checkstyle Plugin|
|https://tinyurl.com/mrxmx9wy|(POC): Static Code Analysis|

