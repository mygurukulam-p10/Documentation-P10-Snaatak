# Commit Sign-Off - Jenkins Shared Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 17-10-2024      | Version 2    | Amit Nagar         | 19-10-2024        |             |             |             |

---

## Table of Contents

1. 💥 [Introduction](#-introduction)
2. ⚙️ [Prerequisites](#-prerequisites)
3. 🔍 [System Requirements](#-system-requirements)
4. 💥 [Steps to Configuration for Commit Sign-Off with Email Notification](#-steps-to-configuration-for-commit-sign-off-with-email-notification)
5. 📄 [Jenkinsfile](#jenkinsfile)
6. 📛 [Conclusion](#-conclusion)
7. 📧 [Contact Information](#-contact-information)
8. 📚 [References](#-references)


---

## ⭐ Introduction 
This document outlines how to configure a Jenkins shared pipeline that enforces commit sign-off, sends email notifications for failures, and includes parameterization for flexibility.

---

## ⚙️ Prerequisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**        | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Git**            | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**| Add your GitHub credentials (e.g., git-token) in Jenkins for repository access. |
| **✔️ Email**          | SMTP configuration for sending emails from Jenkins.                         |

---

## 🔍 System Requirements

### Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                                                |
| **Memory (RAM)**     | Minimum 4 GB                                                      |
| **Storage**          | Minimum 20 GB                                                     |
| **Operating System** | Ubuntu 22.04                                                      |

---
## 💥 Steps to Configure Commit Sign-Off with Email Notification

### 1. 🚀 Create a New Job
- Click on **New Item**.
- Enter a name for your job (e.g., `commit signoff`).

### 2. 🚀 Provide Job Description
- Add a detailed description of what the pipeline will perform.
![Job Description Screenshot](https://github.com/user-attachments/assets/7bd7d526-e38f-4831-953e-69aebd22e4ec)

### 3. 🚀 Configure Pipeline Job
- Choose **Pipeline** as the job type.
- Add your pipeline script for commit signoff in the pipeline configuration.
- Click **Save** to store the configuration.

  
![Pipeline Configuration Screenshot 1](https://github.com/user-attachments/assets/66fa2be5-3193-4384-b4ca-50098bd40b7f)
![Pipeline Configuration Screenshot 2](https://github.com/user-attachments/assets/5ee95dd0-bf7a-4b56-a63e-83b26e251da4)

### 4. 🚀 Run the Pipeline
- Click on **Build** to execute the pipeline for commit signoff.

### 5. 🚀 View Build Completion
- You should see a message indicating that the build has completed successfully.
![Build Completion Screenshot](https://github.com/user-attachments/assets/c46f27bc-c391-480d-9943-3e2970bdfb5e)

### 6. 🚀 Access Console Output
- Click on **Console Output** to view the detailed build logs.
![Console Output Screenshot 1](https://github.com/user-attachments/assets/2e5065cf-55e5-4cde-b63f-c94c9d886739)
![Console Output Screenshot 2](https://github.com/user-attachments/assets/296a9f32-0914-44ac-8cf2-a21912c75206)

### 7. 🚀 Review Dependency Scanning Results
- Examine the console output to review the results of the dependency scanning.  
- Confirm that the email notification has been sent to the specified recipient with the build results.
![Screenshot from 2024-10-22 02-09-32](https://github.com/user-attachments/assets/bfd8591a-fbb6-40f7-ba7c-1c6ca63fb2d6)




---

## Jenkinsfile
```
@Library("shared1") _

@Library("shared1") _

pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from')
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL')
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository')
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
    }

    stages {
        stage('Check Signed-off Commit') {
            steps {
                script {
                    // Invoke shared library function to check commit signoff
                    commitSignoff()
                }
            }
        }
    }

    post {
        always {
            script {
                // Construct email subject and body
                def emailSubject = "Build Status: ${currentBuild.result} - Job ${env.JOB_NAME} [${env.BUILD_NUMBER}]"
                def emailBody = """The current build result is: ${currentBuild.result}
                                Branch: ${params.BRANCH_NAME}
                                Repository: ${params.REPO_URL}
                                Build Number: ${env.BUILD_NUMBER}
                                ${currentBuild.result == 'FAILURE' ? "Error Message: ${currentBuild.description ?: 'N/A'}" : "Build was successful!"}"""
                
                // Call the shared email function
                email(emailSubject, emailBody, params.REPORT_RECIPIENT)
            }
        }
    }
}

```

commitSignoff.groovy
```
def call() {
    // Get the last commit message
    def lastCommitMessage = sh(script: 'git log -1 --pretty=%B', returnStdout: true).trim()

    // Check if the commit contains "Signed-off-by:"
    if (!lastCommitMessage.contains("Signed-off-by:")) {
        currentBuild.result = 'FAILURE'
        error("Commit is not signed off. Please sign off your commit.")
    } else {
        echo "Commit is signed off."
    }
}
```
- [GoLang Shared Library Jenkinsfile](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/GoLang-Shared-Library/CommitSignoff/Jenkinsfile)

- [Jenkins Shared Library Vars](https://github.com/mygurukulam-p10/jenkins-shared-library/tree/main/vars)


## 🏁 Conclusion

The commit signoff process is crucial for maintaining code quality and accountability in software development. It ensures that contributors acknowledge the project's contribution guidelines and take responsibility for their changes. By including a "Signed-off-by" line in your commits, you facilitate a transparent development process and uphold the integrity of the codebase.

## 📞 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Commit Signoff          | [How to Sign Off Commits](https://developercircle.dev/what-is-sign-off-on-git-commit/) |

