
# Golang Shared DAST pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 20-10-2024      | Version 1    | Amit Nagar         | 20-10-2024        |             |             |             |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configure DAST Integration using OWASP ZAP](#-steps-to-configure-dast-integration-using-owasp-zap)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of integrating Dynamic Application Security Testing (DAST) in a Jenkins shared pipeline using OWASP ZAP.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ OWASP ZAP**        | OWASP ZAP must be installed and configured on the Jenkins server.            |
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

## 💥 Steps to Configure DAST Integration using OWASP ZAP

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.  
**--> Enter a name for your job (e.g., `OWASP ZAP DAST Integration`).**  


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.  



### 4. 🚀 Choose **Pipeline** as the job type, add your pipeline script for DAST integration in the pipeline configuration, and click on **Save** to store the configuration.  






### 5. 🚀 Click on **Build** to run the pipeline and perform DAST integration.  



### 6. 🚀 After the build completes, review the stages of the DAST process in the **Console Output**.  



### 7. 🚀 Analyze the Vulnerabilities Identified by OWASP ZAP and Export the Report for Further Review



## Jenkinsfile

```groovy



```
## 📛 Conclusion

The DAST integration using OWASP ZAP ensures that the application undergoes comprehensive security testing during the build process. By incorporating this step into the CI/CD pipeline, teams can identify and remediate vulnerabilities before the application is deployed.

---

## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | [amit.nagar.snaatak@mygurukulam.com](mailto:amit.nagar.snaatak@mygurukulam.com) |

---

## 📚 References

| Topic                  | Reference Link                                                                 |
|------------------------|-------------------------------------------------------------------------------|
| **OWASP ZAP**          | [OWASP ZAP Documentation](https://owasp.org/www-project-zap/)                 |
| **Jenkins Pipeline**   | [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/)   |
| **DAST Testing**       | [DAST Testing with ZAP](https://owasp.org/www-community/activities/dynamic-application-security-testing-dast) |

