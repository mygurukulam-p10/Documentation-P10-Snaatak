# Go-Lang Declarative Pipeline Code Compilation

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | Last Update                    |
|--------------------|------------|--------------|--------------------------------|
| 04-10-2024         | 1.0      | Aayush Gaur  | 22-10-2024           |

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Code Compilation Setup](#Code-Compilation-Setup)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

## 💥 Introduction
Automating the process of building and deploying Go applications can be efficiently done using Continuous Integration (CI) pipelines. Declarative Pipelines in Jenkins allow for structured and readable automation scripts, making the entire Go code compilation process easier to manage and understand.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed on the Jenkins.            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |


## 🔍 System Requirements
| Hardware Specifications | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |

## Plugin Setup - Go Plugin
### Step 1: Search for the Go Plugin & Install
![Screenshot from 2024-10-04 14-34-50](https://github.com/user-attachments/assets/8d0375aa-0c41-45a5-b3a8-6ced03e1943b)

### Step 2: Configure Go in Jenkins
![Screenshot from 2024-10-04 14-40-27](https://github.com/user-attachments/assets/03a80c25-3980-4baa-9e32-08ff4bf7d092)

## 💥 Code Compilation Setup

### Step 1:🚀 Create a New Pipeline Job
- In the Jenkins dashboard, click New Item.
- Name your job (e.g., "GoLang Code Compilation").
- Select Pipeline and click OK.
![Screenshot from 2024-10-16 13-14-55](https://github.com/user-attachments/assets/178ffbf7-c36c-4fb8-8408-9c58e945ee44)


### Step 2:🚀 Configure the Pipeline Script
- In the job configuration, scroll to the Pipeline section.
- Choose Pipeline script from SCM.
- Enter your GitHub repository URL and credentials.
![Screenshot from 2024-10-16 13-15-57](https://github.com/user-attachments/assets/ddb2012d-a4a8-4310-add9-76dcd61cf3df)
![Screenshot from 2024-10-16 13-16-17](https://github.com/user-attachments/assets/84c206d5-0296-4718-8fc8-b1e628353169)

### Step 3:🚀 Trigger the Build
- Go back to your Jenkins job and click Build Now to run the pipeline.


### Step 4:🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-22 11-34-38](https://github.com/user-attachments/assets/c7e5f0b4-6700-4137-a5b7-0d2d653232e7)

### Step 5:🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-22 11-35-40](https://github.com/user-attachments/assets/478b947b-4110-4cff-b2af-e06ef411ffb4)
![Screenshot from 2024-10-22 11-35-47](https://github.com/user-attachments/assets/7b876c20-5ba6-404a-85c5-c47534371d99)
![Screenshot from 2024-10-22 11-35-51](https://github.com/user-attachments/assets/7d44be09-7b71-4355-aea9-003439bac0eb)


### Step 6:🚀 Review the stages of the build process in the console output.
![Screenshot from 2024-10-16 15-49-57](https://github.com/user-attachments/assets/d366953f-f533-439d-a459-6bb56180a90f)

## Jenkinsfile [Pipeline](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Go-Declerative-pipeline/Code%20Compilation/jenkinsfile)
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
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
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





