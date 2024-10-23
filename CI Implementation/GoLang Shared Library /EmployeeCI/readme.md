# EmployeeCI Golang Application CI/CD Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 20-10-2024      | Version 1    | Amit Nagar         | 23-10-2024        |             |             |             |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configure CI/CD Integration for EmployeeCI](#-steps-to-configure-cicd-integration-for-employee-ci)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of integrating Continuous Integration/Continuous Deployment (CI/CD) for the EmployeeCI application using Golang.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Golang**           | Golang must be installed on the Jenkins server for building the application. |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |

---

## 🔍 System Requirements

### Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                                                |
| **Memory (RAM)**     | Minimum 4 GB                                                      |
| **Storage**          | Minimum 20 GB                                                     |
| **Operating System** | Ubuntu 22.04                                                      |

## 💥 Steps to Configure CI/CD Integration for EmployeeCI

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.  
**--> Enter a name for your job (e.g., `EmployeeCI Golang Pipeline`).**  


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.  


### 4. 🚀 Choose **Pipeline** as the job type, add your pipeline script for CI/CD integration in the pipeline configuration, and click on **Save** to store the configuration.  

![Screenshot from 2024-10-24 03-41-40](https://github.com/user-attachments/assets/da6d57df-565d-4f1d-a668-b209173df522)




### 5. 🚀 Click on **Build** to run the pipeline and perform CI/CD integration.  

### 6. 🚀 After the build completes, review the stages of the CI/CD process in the **Console Output**.  


### 7. Email notification





## Jenkinsfile

