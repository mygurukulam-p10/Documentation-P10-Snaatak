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
![Screenshot from 2024-10-06 17-08-21](https://github.com/user-attachments/assets/e5c03431-3bfe-40c0-9fd9-60f0494091cf)


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.  
![Screenshot from 2024-10-07 01-04-38](https://github.com/user-attachments/assets/ce77ceb0-cb07-43e5-87b1-4e65f4782455)


### 4. 🚀 Choose **Pipeline** as the job type, add your pipeline script for DAST integration in the pipeline configuration, and click on **Save** to store the configuration.  
![Screenshot from 2024-10-07 01-05-38](https://github.com/user-attachments/assets/7186df23-195c-4374-878a-30fd6e305ec7)


### 5. 🚀 Click on **Build** to run the pipeline and perform DAST integration.  
![Screenshot from 2024-10-06 17-21-03](https://github.com/user-attachments/assets/3677b74b-d0c6-4213-8fdb-176999890a4b)


### 6. 🚀 After the build completes, review the stages of the DAST process in the **Console Output**.  

![Screenshot from 2024-10-06 19-04-13](https://github.com/user-attachments/assets/8e7592e6-2f02-4d43-8de1-c97ce249bbc6)
![Screenshot from 2024-10-06 19-34-15](https://github.com/user-attachments/assets/3b23452f-db6b-4e0f-968f-bcf61ff37fad)

![Screenshot from 2024-10-07 01-07-03](https://github.com/user-attachments/assets/1c1c83ed-80d5-4a03-b2af-6fd4e29b0e5a)

### 7. 🚀 Analyze the vulnerabilities identified by OWASP ZAP, and export the report for further review.  
![Screenshot from 2024-10-07 00-23-16](https://github.com/user-attachments/assets/c91d898d-a6c7-4bc4-880b-f634641b083e)


## Pipeline
```
node {
    // Define the Go tool name
    def goTool = tool name: 'golang', type: 'go'

    stage("Checkout") {
        git branch: 'main', url: 'git@github.com:mygurukulam-p10/employee-api.git', credentialsId: "amit_cred"
    }

    stage("Install Dependencies") {

        sh "${goTool}/bin/go mod tidy"
    }
    

stage("Install zap"){
    sh 'wget https://github.com/zaproxy/zaproxy/releases/download/v2.15.0/ZAP_2.15.0_Linux.tar.gz'
    sh 'tar -xvf ZAP_2.15.0_Linux.tar.gz'

}
stage('Run ZAP Scan') {
    // Define the path to the ZAP installation dynamically using the job name
    def zapPath = "/var/lib/jenkins/workspace/${env.JOB_NAME}/ZAP_2.15.0/zap.sh"

    // Run the ZAP scan with the dynamically constructed path using double quotes around the entire command
    sh """
        "${zapPath}" -cmd -port 8090 -quickurl http://3.111.35.135:8080/swagger/index.html -quickprogress -quickout ./report.html
    """
}

stage("Publish Dast Report"){

    publishHTML([allowMissing: false, 
     reportDir: "/var/lib/jenkins/workspace/${env.JOB_NAME}/ZAP_2.15.0", 
     reportFiles: 'report.html', 
     reportName: 'DAST Report', 
     reportTitles: 'DAST', useWrapperFileDirectly: true])
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

