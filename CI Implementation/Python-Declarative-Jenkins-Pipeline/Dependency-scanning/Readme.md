# Dependency Scanning- Declarative Jenkins Pipeline <img width="112" alt="image" src="https://github.com/user-attachments/assets/098311ee-16c7-4864-844f-97a2cf913e72">

---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 06-10-2024  | Version 1  | Megha Tyagi     | 06-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Dependency Scanning](#-steps-to-conguration-dependency-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

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
## 🔍 System Requirements

| **Component**      | **Minimum Requirement**           | **Recommended Requirement**    |
|--------------------|-----------------------------------|--------------------------------|
| **CPU**            | Dual-core processor (2 GHz)       | Quad-core processor (3 GHz)    |
| **RAM**            | 4 GB                              | 8 GB or higher                 |
| **Storage**        | 20 GB free disk space             | 50 GB free disk space          |

---

## 💥 Steps to Configuration Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).
<img width="949" alt="New item" src="https://github.com/user-attachments/assets/94557093-db06-4ef9-abc0-d5a1e70d93ea">

### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="941" alt="Description " src="https://github.com/user-attachments/assets/b7bf0eff-5e19-4f76-aeae-caf15ba92aec">


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for static code analysis in the pipeline configuration...>Click on Save to store the configuration.
<img width="914" alt="script" src="https://github.com/user-attachments/assets/3718cb50-a4d4-4bf9-96d4-3a490940a8b6">


### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 6.🚀 Now we are able to see build complete-
![build steps](https://github.com/user-attachments/assets/de15fa25-4c67-43fa-9b95-17f5dd2946f6)


### 7.🚀 Click on Console Output to see the complete build.
<img width="932" alt="console -1" src="https://github.com/user-attachments/assets/945ae170-d5d8-4fd0-a3da-9e6f61771bf9">
<img width="920" alt="console -2" src="https://github.com/user-attachments/assets/853791b0-baee-450f-a747-ccb38df483cf">
<img width="932" alt="console -3" src="https://github.com/user-attachments/assets/cb312415-659d-4533-b916-eac903b37562">
<img width="932" alt="console -4" src="https://github.com/user-attachments/assets/f8931aff-0d68-49ec-b918-9c2e6e7afe8a">

### 8.🚀 Review the stages of the build process in the console output.
<img width="956" alt="final stage" src="https://github.com/user-attachments/assets/05dfb206-10cf-4725-8a2d-dd61b82d803d">


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



