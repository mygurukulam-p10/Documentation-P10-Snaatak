# Dependency Scanning- Declarative Jenkins Pipeline <img width="112" alt="image" src="https://github.com/user-attachments/assets/098311ee-16c7-4864-844f-97a2cf913e72">

---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 06-10-2024  | Version 1  | Megha Tyagi     | 06-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Dependency Scanning](#-steps-to-conguration-dependency-scanning)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This Readme.md provides Dependency scanning is crucial for identifying security vulnerabilities in third-party libraries used by a project. Integrating this into a CI/CD pipeline ensures that only secure dependencies are used, helping to prevent potential security threats. This process is vital for maintaining overall application security.

---

## ⚙️ Pre-requisites

| **Pre-requisite**     | **Description**                                           |
|-----------------------|-----------------------------------------------------------|
| **Python 3.2           | Required for running Python scripts and tools.            |
| **Pip**                | Python package manager for installing dependencies.       | 
| **Pylint**             | Python static code analysis tool for linting.             | 
| **Safety**             | Dependency vulnerability scanner for Python.              | 
| **Git**                | Version control system for cloning repositories.          |
| **Jenkins**            | Automation server for setting up CI/CD pipelines.         | 

---

## 💥 Steps to Configuration Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).
<img width="951" alt="image" src="https://github.com/user-attachments/assets/8b9e87e9-c46a-43b3-a6ca-c51efbdfefc4">


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/397a56ca-d515-49d0-be38-34898620b7e9">


### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM.
![Screenshot 2024-10-07 190107](https://github.com/user-attachments/assets/4fc641ab-5e53-45b1-94fe-1c1e9dd3de93)
![Screenshot 2024-10-07 190125](https://github.com/user-attachments/assets/53feff3b-6d59-4957-834e-43c4079c6f21)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code analysis in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 190216](https://github.com/user-attachments/assets/4a5cd386-e1e0-4b8c-abdc-b2a1f66dc91a)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-07 190744](https://github.com/user-attachments/assets/9e96c6a4-f2fc-4b77-95b8-b91638ff67a8)



### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 190850](https://github.com/user-attachments/assets/e32aee98-2f35-481c-98cc-cf6b999053a2)
![Screenshot 2024-10-07 191635](https://github.com/user-attachments/assets/553b8b64-8df8-4f10-92a8-82a983867f88)
![Screenshot 2024-10-07 191617](https://github.com/user-attachments/assets/33ad5fa3-c074-4659-8ef4-f018148f0578)



### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 190310](https://github.com/user-attachments/assets/82a9371c-59ea-4abf-88cf-757209071496)

---

## 📛 Conclusion
Integrating dependency scanning into a Jenkins declarative pipeline helps identify vulnerabilities in third-party libraries, ensuring secure and reliable software. By automating this process, we can catch security issues early in development and take proactive measures to mitigate risks.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://pypi.org/project/pip-audit/| **Pip Audit** |
|https://safetycli.com/product/safety-cli?utm_source=data&utm_medium=redirect&utm_campaign=data_rd&utm_id=0624&utm_content=marketing| **Safety Docs** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency-Scanning-POC|**Manual POC**|



