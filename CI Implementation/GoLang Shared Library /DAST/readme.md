
# Golang Shared DAST pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 20-10-2024      | Version 1    | Amit Nagar         | 23-10-2024        |             |             |             |

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

![Screenshot from 2024-10-24 03-41-40](https://github.com/user-attachments/assets/da6d57df-565d-4f1d-a668-b209173df522)


![Screenshot from 2024-10-24 03-41-45](https://github.com/user-attachments/assets/b830d728-c8bf-4902-aa80-45aa50a8038f)



### 5. 🚀 Click on **Build** to run the pipeline and perform DAST integration.  



### 6. 🚀 After the build completes, review the stages of the DAST process in the **Console Output**.  
![Screenshot from 2024-10-24 03-42-59](https://github.com/user-attachments/assets/9c581b73-77e3-4f9a-b945-d35ea09c4be6)

![Screenshot from 2024-10-24 03-43-15](https://github.com/user-attachments/assets/0447be89-9c3b-432c-8e56-e5e71c4c9cd3)
![Screenshot from 2024-10-24 03-41-16](https://github.com/user-attachments/assets/d4b5c993-5187-433f-938d-c1a4229de113)



### 7. Email notification
![Screenshot from 2024-10-24 03-30-57](https://github.com/user-attachments/assets/b04473c3-e242-49d5-b80a-a69583ffcb0a)


### 8. 🚀 Analyze the Vulnerabilities Identified by OWASP ZAP and Export the Report for Further Review


## Jenkinsfile

```groovy

@Library('shared1') _

properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'ZAP_URL', defaultValue: 'http://3.111.35.135:8080/swagger/index.html', description: 'URL to scan with ZAP'),
        string(name: 'ZAP_PORT', defaultValue: '8090', description: 'Port to run ZAP on'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Comma-separated email addresses to send the report'),
        string(name: 'REPORT_NAME', defaultValue: 'report1.html', description: 'Name of the DAST report')
    ])
])

pipeline {
    agent any
    stages {
        stage('DAST CI') {
            steps {
                script {
                    def goTool = 'golang'
                    def zapPath = "${env.WORKSPACE}/ZAP/zap.sh"
                    def reportPath = "ZAP/${params.REPORT_NAME}"
                    try {
                        // Check out the specified branch of the repository
                        gitCheckout(params.BRANCH_NAME,params.CREDENTIALS_ID,params.REPO_URL)
                        
                        // Install Go tool
                        goToolInstallation(goTool)
                        
                        // Install ZAP
                        installZap() // Assuming installZAP is defined elsewhere
                        
                        // Run ZAP scan
                        runZAPScan(zapPath, params.ZAP_PORT, params.ZAP_URL, params.REPORT_NAME)
                        
                        // Archive the DAST report
                        archiveReport(reportPath)
                        echo "${params.REPORT_NAME}"
                        currentBuild.result = 'SUCCESS'

                    } catch (Exception e) {
                        currentBuild.result = 'FAILURE'
                        throw e
                    } finally {
                        def buildStatus = currentBuild.result ?: 'SUCCESS'
                        def emailSubject = "DAST Scan Report for ${params.BRANCH_NAME}"
                        def emailBody = """
                            <h1>DAST Scan Report</h1>
                            <p>DAST scan completed for branch <strong>${params.BRANCH_NAME}</strong>.</p>
                            <p>Status: <strong>${buildStatus}</strong></p>
                            <p>Please find the report attached.</p>
                        """
                        // Send email report
                        email(emailSubject, emailBody, params.REPORT_RECIPIENT, reportPath)

                        if (currentBuild.result == 'FAILURE') {
                            echo 'Build failed.'
                        } else {
                            echo 'Build completed successfully.'
                        }

                         cleanWs()
                    }
                }
            }
        }
    }
}


```

- [GoLang-Shared-Library DAST Jenkinsfile](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/GoLang-Shared-Library/DAST/Jenkinsfile)
- [Jenkins Shared Library](https://github.com/mygurukulam-p10/jenkins-shared-library.git)

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

