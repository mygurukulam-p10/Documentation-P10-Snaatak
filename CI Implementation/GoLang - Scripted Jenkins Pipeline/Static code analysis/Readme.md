
# Static Code Analysis - Scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 28-10-2024         |     Tapan       |     Akshay Jain        |         


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

## 💥 Steps to Configure Static Code Analysis

### 1. 🚀 Open Your Jenkins Dashboard
Begin by accessing your Jenkins dashboard to get started with creating a new job.

### 2. 🚀 Create a New Item
- Click on **New Item**.
- Enter a name for your job (e.g., `Static Code Analysis`).
![New Item Screenshot](https://github.com/user-attachments/assets/f0499105-7961-48d1-ad8d-5a7bb9d66029)

### 3. 🚀 Provide a Description for the Pipeline
- Write a detailed description of what the pipeline will perform, so team members understand its purpose.
![Description Screenshot](https://github.com/user-attachments/assets/f344576b-320c-4c6e-87e4-d435f94aaa46)

### 4. 🚀 Choose Pipeline as the Job Type
- Select **Pipeline** as the job type.
- Add your pipeline script for static code analysis in the pipeline configuration area.
- Click on **Save** to store the configuration.
![Pipeline Configuration Screenshot 1](https://github.com/user-attachments/assets/ebeb8762-fbcd-4279-8972-55f1f9911a73)
![Pipeline Configuration Screenshot 2](https://github.com/user-attachments/assets/feeefac5-f633-4e9c-a995-3efd25d0a7aa)

### 5. 🚀 Start the Build Process
- Click on **Build** to initiate the static code analysis pipeline.
![Build Screenshot](https://github.com/user-attachments/assets/bff3c873-923e-4497-ac04-5147a29b3461)

### 6. 🚀 Confirm Build Completion
- After the build has been executed, you should see a confirmation of the build completion.
![Build Completion Screenshot](https://github.com/user-attachments/assets/bb2333cd-73f4-44bc-940b-05a540c9fe81)

### 7. 🚀 View Console Output
- Click on **Console Output** to review the complete build results, including logs and any error messages.
![Console Output Screenshot 1](https://github.com/user-attachments/assets/95e935a9-0ee0-486b-a160-2fb45fb3f538)
![Console Output Screenshot 2](https://github.com/user-attachments/assets/e8bdc109-7fa3-4195-835b-bbb9615cecfb)

### 8. 🚀 Analyze the Stages of Static Code Analysis
- Review the various stages of the static code analysis process displayed in the console output for insights into the analysis results.
![Static Code Analysis Stages Screenshot](https://github.com/user-attachments/assets/3703f13d-472f-4382-915c-b6916a085749)

### 9. 📧 Send Build Report via Email

![Screenshot from 2024-10-21 15-33-50](https://github.com/user-attachments/assets/2a7029af-19c7-4f1c-9000-ae4601719710)


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
## Jenkinsfile
You can find the Jenkinsfile for the static code analysis in the following GitHub repository: [Jenkinsfile Link](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Golang-scripted-pipeline/Static-code-analysis/Jenkinsfile).

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
