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
![Screenshot from 2024-10-09 19-29-41](https://github.com/user-attachments/assets/6d5511b9-8e5a-4441-83e0-bd8737b526a7)



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
node {
    // Define the Go tool name
    def goTool = tool name: 'golang', type: 'go'

    stage("Checkout") {
        git branch: 'main', url: 'git@github.com:mygurukulam-p10/employee-api.git', credentialsId: "amit_cred"
    }

    stage("Install Dependencies") {
        sh "${goTool}/bin/go mod tidy"
    }

    stage("Install ZAP") {
        sh 'wget https://github.com/zaproxy/zaproxy/releases/download/v2.15.0/ZAP_2.15.0_Linux.tar.gz'
        sh 'tar -xvf ZAP_2.15.0_Linux.tar.gz'
    }

    stage('Run ZAP Scan') {
       
        def zapPath = "/var/lib/jenkins/workspace/${env.JOB_NAME}/ZAP_2.15.0/zap.sh"

       
        sh """
            "${zapPath}" -cmd -port 8090 -quickurl http://3.111.35.135:8080/swagger/index.html -quickprogress -quickout ./report.html
        """
    }

    stage("Publish DAST Report") {
        publishHTML([
            allowMissing: false, 
            reportDir: "/var/lib/jenkins/workspace/${env.JOB_NAME}/ZAP_2.15.0", 
            reportFiles: 'report.html', 
            reportName: 'DAST Report', 
            reportTitles: 'DAST', 
            useWrapperFileDirectly: true
        ])
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

