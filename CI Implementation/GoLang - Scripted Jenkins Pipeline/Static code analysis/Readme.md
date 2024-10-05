
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
5. [Pipeline](#pipeline)
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
![Screenshot from 2024-10-05 14-51-39](https://github.com/user-attachments/assets/4dcd0efa-32b9-4a0d-ba3b-1acdc008759f)

### 5. 🚀 Click on **Build** to run the pipeline for static code analysis.
![Screenshot from 2024-10-05 12-54-06](https://github.com/user-attachments/assets/bff3c873-923e-4497-ac04-5147a29b3461)

### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-05 16-12-24](https://github.com/user-attachments/assets/bb2333cd-73f4-44bc-940b-05a540c9fe81)

### 7. 🚀 Click on **Console Output** to see the complete build results.
![Screenshot from 2024-10-05 15-49-37](https://github.com/user-attachments/assets/95e935a9-0ee0-486b-a160-2fb45fb3f538)
![Screenshot from 2024-10-05 15-49-45](https://github.com/user-attachments/assets/e8bdc109-7fa3-4195-835b-bbb9615cecfb)


### 8. 🚀 Review the stages of the static code analysis process in the console output.
![Screenshot from 2024-10-05 16-13-02](https://github.com/user-attachments/assets/3703f13d-472f-4382-915c-b6916a085749)


# Pipeline

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
    stage("Static Code Analysis") {
        script {
            // Set the PATH to include the Go tool directory
            env.PATH = "${goTool}/bin:${env.PATH}"

            sh '''
                echo "Running golangci-lint..."
                golangci-lint run .
            '''
        }
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
