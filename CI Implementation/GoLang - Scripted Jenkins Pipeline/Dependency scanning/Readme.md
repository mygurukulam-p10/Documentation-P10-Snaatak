# Dependency Scanning - OWASP Dependency-Check Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|----------------|----------------|---------------|--------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar         | 05-10-2024        |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Dependency Scanning](#-steps-to-configuration-dependency-scanning)
5. [Pipeline](#pipeline)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of implementing dependency scanning in a project using OWASP Dependency-Check in a Jenkins scripted pipeline.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ OWASP Dependency-Check** | OWASP Dependency-Check must be installed on the Jenkins server.        |
| **✔️ Java**              | Java Development Kit (JDK) must be installed on the Jenkins server.       |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |

---

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |

# Steps to Configuration Dependency Scanning
### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).


### 3. 🚀 Provide a description for the pipeline in detail about what it will perform.

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for dependency scanning in the pipeline configuration...>Click on Save to store the configuration.


### 5. 🚀 Then Click on build to run the pipeline to perform dependency scanning.


### 6. 🚀 Now we are able to see build complete.

### 7. 🚀 Click on Console Output to see the complete build.




### 8. 🚀 Review the results of the dependency scanning in the console output.

# Pipeline




## 🏁 Conclusion
The dependency scanning stage successfully analyzes the project's dependencies, identifying any known vulnerabilities and providing a report to ensure the application is secure.

## 📞 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| OWASP Dependency-Check   | [OWASP Dependency-Check Documentation](https://owasp.org/www-project-dependency-check/) |
| OWASP Dependency-Check CLI | [Dependency-Check CLI Usage](https://jeremylong.github.io/DependencyCheck/dependency-check-maven/) |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
