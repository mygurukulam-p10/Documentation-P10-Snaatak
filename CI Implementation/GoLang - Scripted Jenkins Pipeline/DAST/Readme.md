# Golang Scripted DAST pipeline

---

| ✍Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar | 06-10-2024  | Version 1  | Amit Nagar   | 17-10-2024     |

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
This document provides an overview of integrating Dynamic Application Security Testing (DAST) in a Jenkins scripted pipeline using OWASP ZAP.

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
![Screenshot from 2024-10-06 17-08-21](https://github.com/user-attachments/assets/e5c03431-3bfe-40c0-9fd9-60f0494091cf)


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.  
![Screenshot from 2024-10-07 01-04-38](https://github.com/user-attachments/assets/ce77ceb0-cb07-43e5-87b1-4e65f4782455)


### 4. 🚀 Choose **Pipeline** as the job type, add your pipeline script for DAST integration in the pipeline configuration, and click on **Save** to store the configuration.  
![Screenshot from 2024-10-09 19-29-36](https://github.com/user-attachments/assets/56a9c36a-bc86-4574-b4e5-e48332b19379)
![Screenshot from 2024-10-09 19-34-22](https://github.com/user-attachments/assets/af9e9445-a57a-4c61-aa1e-2175c1b4d201)





### 5. 🚀 Click on **Build** to run the pipeline and perform DAST integration.  
![Screenshot from 2024-10-06 17-21-03](https://github.com/user-attachments/assets/3677b74b-d0c6-4213-8fdb-176999890a4b)


### 6. 🚀 After the build completes, review the stages of the DAST process in the **Console Output**.  

![Screenshot from 2024-10-06 19-04-13](https://github.com/user-attachments/assets/8e7592e6-2f02-4d43-8de1-c97ce249bbc6)
![Screenshot from 2024-10-06 19-34-15](https://github.com/user-attachments/assets/3b23452f-db6b-4e0f-968f-bcf61ff37fad)
![Screenshot from 2024-10-07 01-34-06](https://github.com/user-attachments/assets/d86da67a-76e0-4508-8d0f-882c6d0fe576)


### 7. 🚀 Analyze the Vulnerabilities Identified by OWASP ZAP and Export the Report for Further Review

![Screenshot from 2024-10-07 01-32-13](https://github.com/user-attachments/assets/1bd4ea88-5ab6-4762-87a7-5b4454f0ad42)

## Jenkinsfile

```groovy
// Define properties and parameters
properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'ZAP_URL', defaultValue: 'http://3.111.35.135:8080/swagger/index.html', description: 'URL to scan with ZAP'),
        string(name: 'ZAP_PORT', defaultValue: '8090', description: 'Port to run ZAP on'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the report')
    ])
])

node {
    // Define the Go tool name
    def goTool = tool name: 'golang', type: 'go'
    def zapPath = "${env.WORKSPACE}/ZAP/zap.sh"

    try {
        stage("Checkout") {
            // Checkout code from the repository
            git branch: params.BRANCH_NAME, url: params.REPO_URL, credentialsId: params.CREDENTIALS_ID
        }

        stage("Install Dependencies") {
            // Install Go dependencies
            sh "${goTool}/bin/go mod tidy"
        }

        stage("Install ZAP") {
            // Install ZAP
            sh '''
                wget https://github.com/zaproxy/zaproxy/releases/download/v2.15.0/ZAP_2.15.0_Linux.tar.gz
                tar -xvf ZAP_2.15.0_Linux.tar.gz
                rm -rf ZAP  # Remove the existing directory if it exists
                mv ZAP_2.15.0 ZAP  # Move to desired directory
            '''
        }

        stage("Run ZAP Scan") {
            // Run ZAP scan
            sh """
                "${zapPath}" -cmd -port ${params.ZAP_PORT} -quickurl ${params.ZAP_URL} -quickprogress -quickout ./report1.html
            """
        }

        stage("Publish DAST Report") {
            // Publish the generated DAST report
            publishHTML([
                allowMissing: false, 
                reportDir: "${env.WORKSPACE}/ZAP", 
                reportFiles: 'report1.html', 
                reportName: 'DAST Report', 
                reportTitles: 'DAST'
            ])
        }

        stage("Archive DAST Report") {
            // Archive the DAST report
            archiveArtifacts artifacts: 'ZAP/report1.html', allowEmptyArchive: false
        }
    } catch (Exception e) {
        // Handle any errors that occur during the stages
        currentBuild.result = 'FAILURE'
        throw e
    } finally {
        // Send email regardless of build success or failure
        emailext(
            to: params.REPORT_RECIPIENT,
            subject: "DAST Report - Job ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: """The DAST scan has completed.

            Branch: ${params.BRANCH_NAME}
            Repository: ${params.REPO_URL}
            Credentials ID: ${params.CREDENTIALS_ID}
            ZAP URL: ${params.ZAP_URL}
            ZAP Port: ${params.ZAP_PORT}
            Build Number: ${env.BUILD_NUMBER}
            
            Please find the attached DAST report.
            """,
            attachmentsPattern: 'ZAP/report1.html'
        )
        
        if (currentBuild.result == 'FAILURE') {
            echo 'Build failed.'
        } else {
            echo 'Build completed successfully.'
        }
    }
}

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

