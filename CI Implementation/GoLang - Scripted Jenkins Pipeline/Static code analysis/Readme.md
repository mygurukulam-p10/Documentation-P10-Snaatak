
# Static Code Analysis - Scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar        | 05-10-2024        |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Static Code Analysis](#-steps-to-configuration-for-static-code-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing static code analysis in a Go project using a Jenkins scripted pipeline. The goal is to ensure that the Go code adheres to best practices and is free from common issues.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed on the Jenkins server.            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |
| **✔️ GolangCI-Lint**   | Install GolangCI-Lint on the Jenkins server for static code analysis.       |

---

## 🔍 System Requirements

### Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                                               |
| **Memory (RAM)**     | Minimum 4 GB                                                     |
| **Storage**          | Minimum 20 GB                                                    |
| **Operating System** | Ubuntu 22.04                                                    |

---

## 💥 Steps to Configuration for Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
**-->** Enter a name for your job (e.g., `Static Code Analysis`).

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.

### 4. 🚀 Choose **Pipeline** as the job type. 
**-->** Add your pipeline script for static code analysis in the pipeline configuration... 
**-->** Click on **Save** to store the configuration.

### 5. 🚀 Click on **Build** to run the pipeline for static code analysis.

### 6. 🚀 Now, you should be able to see the build complete.

### 7. 🚀 Click on **Console Output** to see the complete build results.

### 8. 🚀 Review the stages of the static code analysis process in the console output.

## 📛 Conclusion
The static code analysis stage successfully analyzes the Go source code for adherence to coding standards, ensuring that the application is free from common issues and follows best practices.

## 📧 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| GolangCI-Lint          | [GolangCI-Lint Documentation](https://golangci-lint.run) |
