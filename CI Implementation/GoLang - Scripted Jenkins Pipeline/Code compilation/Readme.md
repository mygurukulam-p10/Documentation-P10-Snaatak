# Code Compilation- scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">


---  

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 28-10-2024         |     Tapan       |     Akshay Jain        |             |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Code Compilation](#-steps-to-conguration-code-compilation)
5. [📝 Jenkinsfile](#jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)


## ⭐ Introduction 
This document provides an overview of implementing code compilation in a Go project using a Jenkins scripted pipeline.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Go**               | Go programming language must be installed on the Jenkins server.            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |


---

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |


# Steps to Configuration Code Compilation
### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Code Compilation`).
![Screenshot from 2024-10-05 11-42-53](https://github.com/user-attachments/assets/85f6e0ef-e8c7-48d4-a254-a4ee7e806e3d)

### 3. 🚀 Provide a Description for the Pipeline

#### In this step, you need to provide a clear and detailed description of what the pipeline will perform. This includes outlining the objectives, the code compilation process, and any additional tasks that will be automated through this pipeline..

![Pipeline Description](https://github.com/user-attachments/assets/70b71bf9-2333-46f5-ab21-6ce59dd430d8)

---

### 4. 🚀 Choose **Pipeline** as the Job Type

- Select **Pipeline** as the job type.
- Add your pipeline script for code compilation in the pipeline configuration box. This script will define the steps for code compilation and other build processes.
  
![Add Pipeline Script](https://github.com/user-attachments/assets/95e197ac-ec7d-40b6-a020-931606de5e4c)

![Save Configuration](https://github.com/user-attachments/assets/df35c45f-4848-47c8-8d62-496a5fae0fcb)

---

### 5. 🚀 Click on **Build** to Run the Pipeline

Once you have configured the pipeline, click the **Build** button to run the pipeline and initiate the code compilation process.

![Run Build](https://github.com/user-attachments/assets/7548fea1-4c3e-4c87-87af-a10ce3241090)

---

### 6. 🚀 View the Build Completion Status

After the build process is complete, you will see the build status updated in Jenkins. This confirms that the code compilation was performed successfully.

![Build Complete](https://github.com/user-attachments/assets/62f3a6fa-7a94-4aa7-8b88-9dbaaaf1ebd6)



### 7.🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-05 12-07-04](https://github.com/user-attachments/assets/6bdf0edc-e00e-4cb3-8d51-f015f089da8e)

![Screenshot from 2024-10-05 12-10-02](https://github.com/user-attachments/assets/f7c9c60a-02ca-4386-94f1-9b18a85ca978)

![Screenshot from 2024-10-05 12-10-08](https://github.com/user-attachments/assets/b615a9ee-0b4b-4917-90ad-64f7fc425bb9)

### 8.🚀 Review the stages of the build process in the console output.
![Screenshot from 2024-10-05 12-10-42](https://github.com/user-attachments/assets/a4c8fb82-151a-4de0-87f7-93f29c02e03b)


### 9. Email Notification
Here is the screenshot of the email notification sent after the build process
![Screenshot from 2024-10-21 14-52-31](https://github.com/user-attachments/assets/502290a4-9325-4245-a11c-185017d6c941)

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

        stage("Code Compilation") {
            // Compile the Go application
            sh "${goTool}/bin/go build -o employee main.go"
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
                    Build Number: ${env.BUILD_NUMBER}
                    """
        )
    }
}

```
### Note:
You can find this Jenkinsfile in the following GitHub repository: [Jenkinsfile Repository](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Golang-scripted-pipeline/Code-compilation/Jenkinsfile).

## 🏁 Conclusion
The code compilation stage successfully transforms the Go source code into an executable binary, ensuring that the application is free from syntax errors and meets the necessary requirements.

## 📞 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| Go Testing              | [Go Testing](https://golang.org/pkg/testing/)          |

