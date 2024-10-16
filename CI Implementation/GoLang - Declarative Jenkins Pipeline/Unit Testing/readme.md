# Go-lang - Declarative Jenkins Pipeline for Unit Testing 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Aayush Gaur| 15-10-2024  | Version 1  | Aayush Gaur    | 15-10-2024   |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Unit Testing](#-steps-to-configuration-declarative-pipelines-for-unit-testing)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Go-Lang Unit Testing. Jenkins, as a popular automation server, supports a variety of build configurations.


## ⚙ Pre-requisites
| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed.          |
| **✔️ Git**              | Git must be installed for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |

## 🔍 System Requirements
| Hardware Specifications | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |

## 💥 Steps to Configuration Declarative pipelines for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
 **Enter a name for your job (e.g., `Unit Testing`)**.
![Screenshot from 2024-10-16 14-22-09](https://github.com/user-attachments/assets/31d94ee8-a5cf-4cd2-99e8-d0a994ea7264)

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-16 14-23-26](https://github.com/user-attachments/assets/812973d8-a4e6-43b8-b3c6-9430f74c9cf5)

### 4. 🚀 Choose **Pipeline** as the job type. 
**Add your pipeline script for unit testing in the pipeline configuration.** 
**Click on **Save** to store the configuration.**
![Screenshot from 2024-10-16 14-29-40](https://github.com/user-attachments/assets/52fafceb-8cca-4c2b-91d4-eac5fc82dcbd)
![Screenshot from 2024-10-16 14-30-08](https://github.com/user-attachments/assets/478c998b-7703-4ffe-b41d-bf7ff878ef5a)

### 5. 🚀 Click on Build to run the pipeline for unit testing.
![Screenshot from 2024-10-16 14-31-58](https://github.com/user-attachments/assets/9f752c6b-e02d-490d-a4d8-614108fc149e)


### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-16 15-45-53](https://github.com/user-attachments/assets/dc22a66f-c3ac-4860-b0cc-fedeb3eaf9cf)

### 7.🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-16 15-47-19](https://github.com/user-attachments/assets/30ace96a-faab-4359-ad6d-19ca0dcbf781)
![Screenshot from 2024-10-16 15-48-11](https://github.com/user-attachments/assets/46259054-14ea-45f3-82f0-bd1f31f27b43)
![Screenshot from 2024-10-16 15-48-33](https://github.com/user-attachments/assets/8dd8e210-f5a6-4aec-9aaf-683a931ff627)

### 8.🚀 Review the stages of the build process in the console output.
![Screenshot from 2024-10-16 15-49-57](https://github.com/user-attachments/assets/d366953f-f533-439d-a459-6bb56180a90f)

## Jenkinsfile
```
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/mygurukulam-p10/employee-api.git', credentialsId: 'aayush_cred'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install dependencies using Go modules
                sh '/usr/local/go/bin/go mod tidy'
            }
        }
        stage('Compile Code') {
            steps {
                // Compile the Go application
                sh '/usr/local/go/bin/go build -v ./...'
            }
        }
    }
    post {
        always {
            // Clean up workspace after job completion
            cleanWs()
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
```
## 🏁 Conclusion
The code compilation stage successfully transforms the Go source code into an executable binary, ensuring that the application is free from syntax errors and meets the necessary requirements.

## 📞 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Aayush Gaur | aayush.gaur.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| Go Testing              | [Go Testing](https://golang.org/pkg/testing/)          |

