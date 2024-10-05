# Unit Testing - Scripted Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|---------------|----------------|---------------|-------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar        | 05-10-2024        |

---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Unit Testing](#-steps-to-configuration-for-unit-testing)
5. [Pipeline](#pipeline)
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
![Screenshot from 2024-10-05 16-46-28](https://github.com/user-attachments/assets/8d0576ce-ffbe-4b19-9423-f476db4db53f)

### 5. 🚀 Click on **Build** to run the pipeline for unit testing.
![Screenshot from 2024-10-05 16-39-44](https://github.com/user-attachments/assets/f858f2c1-ad1d-4cae-931f-64341b956a87)

### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-05 16-46-45](https://github.com/user-attachments/assets/56ead5a2-e956-4aba-8643-48c91018c420)

### 7. 🚀 Click on **Console Output** to see the complete build results.
![Screenshot from 2024-10-05 16-45-58](https://github.com/user-attachments/assets/fba85534-e64b-4c33-bb79-7dc8223aeb25)
![Screenshot from 2024-10-05 16-46-06](https://github.com/user-attachments/assets/beb22ec8-12ce-4a1b-a8f3-a55625faa6b1)


### 8. 🚀 Review the results of the unit testing process in the console output.
![Screenshot from 2024-10-05 16-47-23](https://github.com/user-attachments/assets/bc3a7d99-0190-4390-8480-ce501a7fafc4)

# Pipeline

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

    stage("Unit Testing") {
        script {
            sh '''
                echo "Running unit tests..."
                go test ./... -v
            '''
        }
    }
}
```

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

