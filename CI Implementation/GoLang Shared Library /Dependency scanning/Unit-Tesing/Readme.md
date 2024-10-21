# Unit Testing - Shared Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 21-10-2024         |             |             |             |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Unit Testing](#-steps-to-configuration-for-unit-testing)
5. [Jenskinfile](#jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing unit testing in a Go project using a Jenkins shared pipeline. The aim is to ensure that the Go code is tested effectively, helping to identify bugs and ensure code quality.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed on the Jenkins server.            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |
| **✔️ Testing Framework**| Ensure you have a testing framework (like `testing` and `testify`) available for Go. |

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

## 💥 Steps to Configuration for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
**-->** Enter a name for your job (e.g., `Unit Testing`).


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-16 02-43-22](https://github.com/user-attachments/assets/fa9874ae-6fc4-431b-9eab-1144e1435cdf)


### 4. 🚀 Choose **Pipeline** as the job type. 
**-->** Add your pipeline script for unit testing in the pipeline configuration... 
**-->** Click on **Save** to store the configuration.
![Screenshot from 2024-10-09 19-29-36](https://github.com/user-attachments/assets/798e66bc-7ab3-43ea-9eb4-562af49b46c2)

![Screenshot from 2024-10-16 12-48-05](https://github.com/user-attachments/assets/38ee487a-f306-4d82-8606-49d8985596e2)


### 5. 🚀 Click on **Build** to run the pipeline for unit testing.



### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-16 12-28-57](https://github.com/user-attachments/assets/3e0aa0fe-bbfa-4b4b-ad3a-8a66f64fbe54)
### 7. 🚀 Click on **Console Output** to see the complete build results.
![Screenshot from 2024-10-16 12-28-37](https://github.com/user-attachments/assets/0efa6d7b-054b-454f-80fa-8cc60c654658)

![Screenshot from 2024-10-16 12-28-46](https://github.com/user-attachments/assets/5ccd25e2-9f07-47b8-a91d-865a4758aa6c)



### 8. 🚀 Review the results of the unit testing process in the console output.
![Screenshot from 2024-10-16 12-29-30](https://github.com/user-attachments/assets/24a58f66-f013-409c-8e9c-a893819b43b7)


# Jenskinfile


```groovy
@Library("shared1") _  

properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
    ])
])

node {
    def buildResult = 'SUCCESS' // Initialize build result variable
    try {
        // Git Checkout
        def branch = params.BRANCH_NAME
        def creds = params.CREDENTIALS_ID
        def url = params.REPO_URL
        def toolName = 'golang'
        
        echo "Starting Git checkout on branch: ${branch} from URL: ${url} using credentials ID: ${creds}"
        gitCheckout(branch, creds, url)
        echo "Git checkout completed successfully."

        // Tool Installation
        goToolInstallation(toolName)  // Install Go tool
        goInstallDependency()          // Install Go dependencies
        
        // Golang Unit Testing
        golangUnitTesting()            // Run unit tests

    } catch (Exception e) {
        buildResult = 'FAILURE' // Update build result on failure
        echo "An error occurred: ${e.message}"
    } finally {
        // Send email notification
        emailext(
            to: params.REPORT_RECIPIENT,
            subject: "Build Status: ${buildResult} - Job ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: """The current build result is: ${buildResult}

                    Branch: ${params.BRANCH_NAME}
                    Repository: ${params.REPO_URL}
                    Build Number: ${env.BUILD_NUMBER}
                    """
        )
    }
}
```

## var folder groovy files
goInstallDependency.groovy

```
def call (){
    stage("Install Dependencies") {
        // Use the Go tool to tidy dependencies
        sh "go mod tidy"
    }
}
```


gitCheckout.groovy
```
def call (String branch, String creds, String url) {
        stage('Checkout') {
            // Perform the Git checkout
            script{

                git branch: "${branch}", url: "${url}", credentialsId: "${creds}"
            }
            
        }
        return "Checkout successful for branch: ${branch}"
    }
```


golangUnitTesing.groovy

```
def call(){
    stage("Unit Testing") {
        script {
            sh '''
                echo "Running unit tests..."
                go test ./... -coverprofile=coverage.out || true
            '''
        }
    }
}

```
[GoLang Shared Library Jenkinsfile](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/GoLang-Shared-Library/Unit-Tesing/Jenkinsfile)

[Jenkins Shared Library Vars](https://github.com/mygurukulam-p10/jenkins-shared-library/tree/main/vars)


## 📛 Conclusion
The unit testing stage successfully executes the Go tests, helping to ensure that the code behaves as expected and identifying any issues before deployment. This integration within the Jenkins pipeline enhances the overall development workflow, ensuring quality and reliability in the codebase.

## 📧 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                       |
|-------------------------|-------------------------------------|
| Go Testing              | [Go Testing Documentation](https://golang.org/pkg/testing/) |
| Go Command              | [Go Command](https://golang.org/ref/go) |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| Go Test                 | [Go Test Documentation](https://golang.org/pkg/testing/#hdr-Testable) |

