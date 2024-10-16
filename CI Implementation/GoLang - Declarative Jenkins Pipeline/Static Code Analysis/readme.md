# Static Code Analysis - Declarative Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Aayush Gaur     | 16-10-2024     | Version 1     | Aayush Gaur        | 16-10-2024        |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Static Code Analysis](#-steps-to-configuration-for-static-code-analysis)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing static code analysis in a Go project using a Jenkins declarative pipeline. The goal is to ensure that the Go code adheres to best practices and is free from common issues.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed.            |
| **✔️ Git**              | Git must be installed on the Jenkins for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |
| **✔️ GolangCI-Lint**   | Install GolangCI-Lint on the Jenkins server for static code analysis.       |

## 🔍 System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                                               |
| **Memory (RAM)**     | Minimum 4 GB                                                     |
| **Storage**          | Minimum 20 GB                                                    |
| **Operating System** | Ubuntu 22.04                                                    |

## 💥 Steps to Configuration for Static Code Analysis

### Step 1: 🚀 Open your Jenkins Dashboard.

### Step 2:  🚀 Click on **New Item
**Enter a name for your job (e.g., GoLang Static Code Analysis) & Choose Pipeline.
![Screenshot from 2024-10-16 18-02-30](https://github.com/user-attachments/assets/60fd1474-9cd6-4d82-ad04-5af422590113)

### Step 3: 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-16 18-04-22](https://github.com/user-attachments/assets/0e8fd60e-d555-4a3c-942f-368206ba837a)

### Step 4: Choose Pipeline as the job type
- **Add your pipeline script for static code analysis in the pipeline configuration**. 
- **Click on Save to store the configuration**.
