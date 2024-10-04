# Code Coverage- Declarative Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">


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
This document provides an overview of implementing code coverage in a Python project using a Jenkins declarative pipeline. Code coverage is a metric that measures how much of the source code is executed while running automated tests. By integrating code coverage tools such as pytest-cov, we can ensure that their test suite effectively covers critical parts of the codebase, leading to better software quality and reliability. The steps outlined in this pipeline automate the testing and code coverage reporting process.

---

## ⚙️ Pre-requisites

| Requirement         | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Python Version**   | Python 3.10 or later.                                                       |
| **Jenkins**          | Jenkins installed and configured.                                           |
| **Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **Python3-venv**     | Install the `python3-venv` package on the Jenkins server for virtualenv setup.|
| **pip**              | Python package installer (pip) must be available to install dependencies.   |
| **pytest**           | pytest and pytest-cov packages must be installed for testing and coverage.  |
| **Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access.|

---

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU (4-core recommended)                           |
| **Memory (RAM)**     | Minimum 4 GB (8 GB recommended)                                   |
| **Storage**          | Minimum 20 GB of free disk space (SSD recommended for performance)|
| **Operating System** | Ubuntu 20.04 or later (or any compatible Linux distribution)      |

---

## 💥 Steps to Configuration Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Code Coverage`).
<img width="942" alt="item" src="https://github.com/user-attachments/assets/f6ace938-8206-4294-a6ee-88742d4d7851">


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="946" alt="description" src="https://github.com/user-attachments/assets/337ceba5-2491-4f45-9283-07a841e989b0">


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for code coverage in the pipeline configuration...>Click on Save to store the configuration.
<img width="927" alt="script" src="https://github.com/user-attachments/assets/a0ee88c3-1ed4-4e05-832b-a69ff1d42057">


### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 6.🚀 Now we are able to see build complete-
<img width="947" alt="build status" src="https://github.com/user-attachments/assets/eb81d3ce-1226-4395-8537-aa851b3ab6d1">


### 7.🚀 Click on Console Output to see the complete build.
<img width="947" alt="console output -1" src="https://github.com/user-attachments/assets/c825e840-5480-48f3-a550-1b627f5da9aa">
<img width="940" alt="console output -2" src="https://github.com/user-attachments/assets/5cc5c207-ce1c-4c87-a3e0-f19caa6acd11">
<img width="931" alt="console output -3" src="https://github.com/user-attachments/assets/f3a60b55-6aa5-46e0-870c-65181007b46c">


### 8.🚀 Review the stages of the build process in the console output.
<img width="959" alt="build steps status" src="https://github.com/user-attachments/assets/33548ca1-b66b-4132-a6ae-0126cb254872">

---

## 📛 Conclusion
In summary, implementing code coverage in your project is essential for ensuring code quality and reliability. By utilizing tools like `pytest` and `pytest-cov`, you can systematically evaluate how well your tests cover your codebase. This practice not only helps identify untested areas but also encourages writing comprehensive test cases, ultimately leading to more robust and maintainable code. Regularly monitoring code coverage will enhance your development workflow, foster collaboration among team members, and contribute to the overall success of your software projects.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@ganesharavind124/building-a-jenkins-pipeline-for-code-quality-and-continuous-integration-4c57f0365838| **Medium** |
|https://reddeppa-s.medium.com/jenkins-pipeline-as-code-21b71d8f823a| **Medium** |





