
# Static Code Analysis - Scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar        | 05-10-2024        |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Static Code Analysis](#-steps-to-configuration-for-static-code-analysis)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing static code analysis in a Go project using a Jenkins scripted pipeline. The goal is to ensure that the Go code adheres to best practices and is free from common issues.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed on the Jenkins server.            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |
| **✔️ GolangCI-Lint**   | Install GolangCI-Lint on the Jenkins server for static code analysis.       |

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

## 💥 Steps to Configuration for Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
**-->** Enter a name for your job (e.g., `Static Code Analysis`).
![Screenshot from 2024-10-05 12-51-28](https://github.com/user-attachments/assets/f0499105-7961-48d1-ad8d-5a7bb9d66029)

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-05 12-54-47](https://github.com/user-attachments/assets/f344576b-320c-4c6e-87e4-d435f94aaa46)

### 4. 🚀 Choose **Pipeline** as the job type. 
**-->** Add your pipeline script for static code analysis in the pipeline configuration... 
**-->** Click on **Save** to store the configuration.
![Screenshot from 2024-10-09 19-29-36](https://github.com/user-attachments/assets/ebeb8762-fbcd-4279-8972-55f1f9911a73)

![Screenshot from 2024-10-09 19-38-09](https://github.com/user-attachments/assets/feeefac5-f633-4e9c-a995-3efd25d0a7aa)


### 5. 🚀 Click on **Build** to run the pipeline for static code analysis.
![Screenshot from 2024-10-05 12-54-06](https://github.com/user-attachments/assets/bff3c873-923e-4497-ac04-5147a29b3461)

### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-05 16-12-24](https://github.com/user-attachments/assets/bb2333cd-73f4-44bc-940b-05a540c9fe81)

### 7. 🚀 Click on **Console Output** to see the complete build results.
![Screenshot from 2024-10-05 15-49-37](https://github.com/user-attachments/assets/95e935a9-0ee0-486b-a160-2fb45fb3f538)
![Screenshot from 2024-10-05 15-49-45](https://github.com/user-attachments/assets/e8bdc109-7fa3-4195-835b-bbb9615cecfb)


### 8. 🚀 Review the stages of the static code analysis process in the console output.
![Screenshot from 2024-10-05 16-13-02](https://github.com/user-attachments/assets/3703f13d-472f-4382-915c-b6916a085749)


# Jenkinsfile

```
properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
    ])
])

node {
    // Define the Go tool name
    def goTool = tool name: 'golang', type: 'go'

    try {
        stage("Checkout") {
            // Checkout the source code from the Git repository using parameters
            git branch: params.BRANCH_NAME, url: params.REPO_URL, credentialsId: params.CREDENTIALS_ID
        }

        stage("Install Dependencies") {
            // Use the Go tool to tidy dependencies
            sh "${goTool}/bin/go mod tidy"
        }

        stage("Static Code Analysis") {
            script {
                // Set the PATH to include the Go tool directory
                env.PATH = "${goTool}/bin:${env.PATH}"

                // Run static code analysis with golangci-lint
                sh '''
                    echo "Running golangci-lint..."
                    golangci-lint run .
                '''
            }
        }

        // Mark the build as successful
        currentBuild.result = 'SUCCESS'

    } catch (Exception e) {
        // Mark the build as failed if any exception occurs
        currentBuild.result = 'FAILURE'
        throw e
    } finally {
        // Send an email with the current build result and parameters
        emailext(
            to: params.REPORT_RECIPIENT,
            subject: "Build Status: ${currentBuild.result} - Job ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: """The current build result is: ${currentBuild.result}

                    Branch: ${params.BRANCH_NAME}
                    Repository: ${params.REPO_URL}
                    Credentials ID: ${params.CREDENTIALS_ID}
                    Build Number: ${env.BUILD_NUMBER}
                    """
        )
    }
}

```
## 📛 Conclusion
The static code analysis stage successfully analyzes the Go source code for adherence to coding standards, ensuring that the application is free from common issues and follows best practices.

## 📧 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| GolangCI-Lint          | [GolangCI-Lint Documentation](https://golangci-lint.run) |
