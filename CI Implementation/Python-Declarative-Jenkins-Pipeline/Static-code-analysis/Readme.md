# Static Code Anaylsis- Declarative Jenkins Pipeline <img width="33" alt="logo" src="https://github.com/user-attachments/assets/52548837-3a11-4ee6-858f-d04223c52fcc">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 04-10-2024  | Version 1  | Megha Tyagi     | 04-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Static Code Analysis](#-steps-to-conguration-static-code-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
Static code analysis is essential for maintaining code quality and identifying potential issues before deployment. This document outlines the steps to set up a Jenkins declarative pipeline for static code analysis using Python and Pylint. Integrating this process into CI/CD helps ensure cleaner, more reliable code.

---

## ⚙️ Pre-requisites

| Requirement                        | Description                                                      |
|------------------------------------|------------------------------------------------------------------|
| Jenkins Installed                   | Ensure Jenkins is installed and properly configured on your server. |
| Git Plugin for Jenkins              | The Git plugin must be installed in Jenkins to allow for repository checkouts. |
| Python and Pylint Installed         | Python and Pylint should be installed in the environment where Jenkins runs. |
| Java Installed                      | Java is required for Jenkins to run effectively. Ensure you have an appropriate version of the Java Runtime Environment (JRE). |

---
## 🔍 System Requirements

| Component          | Minimum Requirements                                    | Recommended Requirements                        |
|--------------------|--------------------------------------------------------|--------------------------------------------------|
| CPU                | 2 cores                                                | 4 cores or more                                  |
| RAM                | 4 GB                                                  | 8 GB or more                                    |
| Disk Space         | 10 GB available (for Jenkins and project files)      | 20 GB or more                                   |
| Operating System    | Linux, Windows, or macOS (64-bit)                     | Latest stable version of Linux (Ubuntu/CentOS), Windows Server, or macOS |

---

## 💥 Steps to Configuration Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
<img width="946" alt="new item" src="https://github.com/user-attachments/assets/e8ce676b-3217-4ec7-a0ba-c92b19ba9fcd">

### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="944" alt="description" src="https://github.com/user-attachments/assets/b1066678-79ab-4517-b716-12a4986b4ba0">


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for static code analysis in the pipeline configuration...>Click on Save to store the configuration.
<img width="947" alt="code script" src="https://github.com/user-attachments/assets/722a5ff4-456f-432d-ab79-7ec010b0cd50">


### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 6.🚀 Now we are able to see build complete-
<img width="948" alt="build status" src="https://github.com/user-attachments/assets/2b13d03a-dc5f-4785-acb3-187b511340eb">


### 7.🚀 Click on Console Output to see the complete build.
<img width="926" alt="console-1" src="https://github.com/user-attachments/assets/1c1b7918-6d6e-42e4-9ec2-30d4b5687fef">
<img width="923" alt="console-2" src="https://github.com/user-attachments/assets/02255e67-6f19-4f87-8369-487699fc263e">
<img width="925" alt="console-3" src="https://github.com/user-attachments/assets/b686d1d9-fd75-4b8c-80fa-02cf213e76ab">

### 8.🚀 Review the stages of the build process in the console output.
<img width="957" alt="build step" src="https://github.com/user-attachments/assets/653a9abe-2e74-491e-80cc-7cef2fd37208">
---

## 📛 Conclusion
Integrating static code analysis into a Jenkins declarative pipeline enhances code quality by identifying issues early in development. By following the outlined steps, teams can automate the analysis process with Python and Pylint. This practice fosters a culture of quality, resulting in more maintainable.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@tlilyskander/static-code-analysis-with-pylint-49a078f029cf| **Medium** |
|https://stackoverflow.com/questions/61110808/how-to-do-code-analysis-for-python-inheritance| **Stackoverflow** |
|https://tinyurl.com/ycxxt6py|**Manual POC**|


