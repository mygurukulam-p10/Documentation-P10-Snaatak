# Unit Testing - Scripted Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar        | 09-10-2024        |

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
This document provides an overview of implementing unit testing in a Go project using a Jenkins scripted pipeline. The aim is to ensure that the Go code is tested effectively, helping to identify bugs and ensure code quality.

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
![Screenshot from 2024-10-05 16-38-53](https://github.com/user-attachments/assets/1c1e543d-fe5d-40db-ac7e-b1efabf71c3b)

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-05 16-51-50](https://github.com/user-attachments/assets/7b04590f-5f0a-4886-8d46-62cfc2c2473a)

### 4. 🚀 Choose **Pipeline** as the job type. 
**-->** Add your pipeline script for unit testing in the pipeline configuration... 
**-->** Click on **Save** to store the configuration.
![Screenshot from 2024-10-09 19-29-36](https://github.com/user-attachments/assets/798e66bc-7ab3-43ea-9eb4-562af49b46c2)

![Screenshot from 2024-10-09 19-43-33](https://github.com/user-attachments/assets/606a7046-1757-432a-b354-0159cfbe526a)

### 5. 🚀 Click on **Build** to run the pipeline for unit testing.
![Screenshot from 2024-10-05 16-39-44](https://github.com/user-attachments/assets/f858f2c1-ad1d-4cae-931f-64341b956a87)

### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-05 16-46-45](https://github.com/user-attachments/assets/56ead5a2-e956-4aba-8643-48c91018c420)

### 7. 🚀 Click on **Console Output** to see the complete build results.
![Screenshot from 2024-10-05 16-45-58](https://github.com/user-attachments/assets/fba85534-e64b-4c33-bb79-7dc8223aeb25)
![Screenshot from 2024-10-05 16-46-06](https://github.com/user-attachments/assets/beb22ec8-12ce-4a1b-a8f3-a55625faa6b1)


### 8. 🚀 Review the results of the unit testing process in the console output.
![Screenshot from 2024-10-05 16-47-23](https://github.com/user-attachments/assets/bc3a7d99-0190-4390-8480-ce501a7fafc4)

### 9. 🚀 Email Notification

**After the build process, an email will be sent to the specified recipient, containing:**
- The current build result (Success or Failure).
![Screenshot from 2024-10-21 18-04-17](https://github.com/user-attachments/assets/c43a983e-8107-4c2a-961f-a64402353472)


# Jenskinfile

```groovy
properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
    ])
])

node {
    def goTool = tool name: 'golang', type: 'go'
    
    // Set the PATH to include Go binary directory
    env.PATH = "${goTool}/bin:${env.PATH}"

    try {
        stage("Checkout") {
            // Checkout the source code from the Git repository using parameters
            git branch: params.BRANCH_NAME, url: params.REPO_URL, credentialsId: params.CREDENTIALS_ID
        }

        stage("Install Dependencies") {
            // Use the Go tool to tidy dependencies
            sh "go mod tidy"
        }

        stage("Unit Testing") {
            script {
                // Run unit tests and generate a coverage report
                sh '''
                    echo "Running unit tests..."
                    go test ./... -coverprofile=coverage.out
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
                    """,
            attachmentsPattern: 'coverage.out' // Attach the coverage report
        )
    }
}

```

**Note:** You can find this Jenkinsfile at the following URL: [Jenkinsfile for Unit Testing](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Golang-scripted-pipeline/Unit-Testing/Jenkinsfile)


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

