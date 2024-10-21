
# Bug Analysis - Scripted Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar        | 09-10-2024        |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Bug Analysis](#-steps-to-configuration-for-bug-analysis)
5. [Jenkinsfile](#pipeline)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing bug analysis in a Go project using Golang. The aim is to help identify and fix bugs effectively, ensuring code quality and reliability.

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
| **Memory (RAM)**     | Minimum 8 GB                                                     |
| **Storage**          | Minimum 20 GB                                                    |
| **Operating System** | Windows, macOS, or Linux (latest stable versions)               |

---

## 💥 Steps to Configure Bug Analysis

### 1. 🚀 Open Your Jenkins Dashboard
Begin by navigating to your Jenkins dashboard. This is the main interface where you can manage all your jobs and configurations.

### 2. 🚀 Create a New Item
- Click on **New Item**.
- Enter a name for your job (e.g., `Bug Analysis`).

![New Item Screenshot](https://github.com/user-attachments/assets/c5005c0d-6a5b-4420-9095-774dc3269006)

### 3. 🚀 Provide a Job Description
- In the description field, provide details about what the pipeline will perform. This helps others understand the purpose of the job.

![Job Description Screenshot](https://github.com/user-attachments/assets/ed9a7530-b788-46ac-9a27-8b8962e68460)

### 4. 🚀 Select Job Type
- Choose **Pipeline** as the job type.
- Add your pipeline script for bug analysis in the pipeline configuration box.
- Click on **Save** to store the configuration.

![Choose Pipeline Screenshot](https://github.com/user-attachments/assets/a1f2fd1e-5686-424b-b2f1-f6ba9f5965dd)
![Save Configuration Screenshot](https://github.com/user-attachments/assets/a5be010c-8306-415e-9b6a-b0ef69bf7a35)

### 5. 🚀 Run the Pipeline
- Click on **Build** to execute the pipeline for bug analysis.

![Build Screenshot](https://github.com/user-attachments/assets/505b5117-910b-4e44-93e9-6a19aa6bf0da)

### 6. 🚀 Verify Build Completion
After the build process finishes, you should see a notification indicating the build is complete.

![Build Complete Screenshot](https://github.com/user-attachments/assets/e44e97f3-3c40-4a78-a8c8-6fc2ff6f601f)

### 7. 🚀 Access Console Output
- Click on **Console Output** to view detailed results of the build process. This will provide insight into any errors or warnings that occurred during the execution.

![Console Output Screenshot](https://github.com/user-attachments/assets/88ac7059-2000-4b54-a214-0e4675d3619c)
![Console Output Detail Screenshot](https://github.com/user-attachments/assets/59c7a636-42e0-495c-aa12-ad721d360fce)

### 8. 🚀 Review Bug Analysis Results
In the console output, carefully review the stages of the bug analysis process. This will help you identify any issues that need to be addressed in your code.

### 9. 🚀 Email Notification
Once the bug analysis is complete, an email notification will be sent to the specified recipient with the build results. This can be configured in your Jenkins pipeline to include details such as build status, branch name, and any relevant information.

> **Note:** Ensure that the email extension plugin is installed and configured in Jenkins for this feature to work properly.



## Jenkinsfile
```


properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'EMAIL_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email recipient for build notifications')
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

        stage("Linting") {
            script {
                // Set the PATH to include the Go tool directory
                env.PATH = "${goTool}/bin:${env.PATH}"

                sh '''
                    echo "Running golangci-lint..."
                    golangci-lint run ./... || true
                '''
            }
        }

        stage('Generate Report') {
            // Generate an HTML report for golangci-lint
            sh 'golangci-lint run ./... --out-format html > report.html || true'
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
            to: params.EMAIL_RECIPIENT,
            subject: 'Build Status - ${currentBuild.result}',
            body: """The current build result is: ${currentBuild.result}

                    Branch: ${params.BRANCH_NAME}
                    Repository: ${params.REPO_URL}
                    """
        )
        
        // Attach the generated report if successful
        if (currentBuild.result == 'SUCCESS') {
            emailext(
                to: params.EMAIL_RECIPIENT,
                subject: 'Lint Report',
                body: 'Please find the attached lint report.',
                attachmentsPattern: 'report.html'
            )
        }
    }
}

}


```
## 📛 Conclusion
Effective bug analysis  helps developers identify and fix issues quickly, ensuring the reliability of their Go applications. By leveraging Golang's debugging and testing features, the development workflow becomes more efficient, ultimately enhancing code quality.

## 📧 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References


| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| GolangCI-Lint          | [GolangCI-Lint Documentation](https://golangci-lint.run) |
