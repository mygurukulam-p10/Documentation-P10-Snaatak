# DAST Integration using OWASP ZAP

---

| ✍Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar | 06-10-2024  | Version 1  | Amit Nagar   | 06-10-2024     |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configure DAST Integration using OWASP ZAP](#-steps-to-configure-dast-integration-using-owasp-zap)
5. [Pipeline](#pipeline)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of integrating Dynamic Application Security Testing (DAST) in a Jenkins scripted pipeline using OWASP ZAP.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ OWASP ZAP**        | OWASP ZAP must be installed and configured on the Jenkins server.            |
| **✔️ Docker**           | Docker must be installed if you want to use the OWASP ZAP Docker image.       |
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
![New Item Screenshot](https://github.com/user-attachments/assets/85f6e0ef-e8c7-48d4-a254-a4ee7e806e3d)

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.  
![Description Screenshot](https://github.com/user-attachments/assets/70b71bf9-2333-46f5-ab21-6ce59dd430d8)

### 4. 🚀 Choose **Pipeline** as the job type, add your pipeline script for DAST integration in the pipeline configuration, and click on **Save** to store the configuration.  
![Pipeline Configuration Screenshot](https://github.com/user-attachments/assets/57cbffb8-526d-41f1-91c4-920cf2b0b84d)

### 5. 🚀 Click on **Build** to run the pipeline and perform DAST integration.  
![Build Screenshot](https://github.com/user-attachments/assets/7548fea1-4c3e-4c87-87af-a10ce3241090)

### 6. 🚀 After the build completes, review the stages of the DAST process in the **Console Output**.  
![Console Output Screenshot](https://github.com/user-attachments/assets/6bdf0edc-e00e-4cb3-8d51-f015f089da8e)

### 7. 🚀 Analyze the vulnerabilities identified by OWASP ZAP, and export the report for further review.  
![Analysis Screenshot](https://github.com/user-attachments/assets/a4c8fb82-151a-4de0-87f7-93f29c02e03b)

## Pipeline

```groovy
node {
    // Define the OWASP ZAP Docker image
    def zapImage = 'owasp/zap2docker-stable'
    
    stage("Checkout") {
        // Checkout the source code from the Git repository
        git branch: 'main', url: 'git@github.com:mygurukulam-p10/web-app.git', credentialsId: "amit_cred"
    }

    stage("Start ZAP Docker Container") {
        // Pull and start the OWASP ZAP container
        sh "docker pull ${zapImage}"
        sh "docker run -d --name zap -u zap -p 8080:8080 ${zapImage}"
    }

    stage("Run DAST Scan") {
        // Execute a ZAP active scan on the target application
        sh "docker exec zap zap-full-scan.py -t http://web-app.local -r zap_report.html"
    }
   
    stage("Publish Report") {
        // Copy the ZAP report to the Jenkins workspace
        sh "docker cp zap:/home/zap/zap_report.html ${WORKSPACE}/zap_report.html"
        
        // Archive the report
        archiveArtifacts artifacts: 'zap_report.html', allowEmptyArchive: true
    }

    stage("Stop ZAP Docker Container") {
        // Stop and remove the ZAP Docker container
        sh "docker stop zap && docker rm zap"
    }
}

