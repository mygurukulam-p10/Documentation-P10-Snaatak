# Commit Sign-Off - Jenkins Shared Pipeline with Email Notification and Parameterization

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 17-10-2024      | Version 2    | Amit Nagar         | 17-10-2024        |             |             |             |

---

## Table of Contents

1. [💥 Introduction](#-introduction)
2. [⚙️ Prerequisites](#-prerequisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Commit Sign-Off with Email Notification](#-steps-to-configuration-for-commit-sign-off-with-email-notification)
5. [Jenkinsfile](#jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

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

## 💥 Steps to Configuration for Commit Sign-Off with Email Notification

### 1. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `commit signoff`).

### 2. 🚀 Provide a description for the pipeline in detail about what it will perform.
![Screenshot from 2024-10-20 02-37-16](https://github.com/user-attachments/assets/7bd7d526-e38f-4831-953e-69aebd22e4ec)


### 3. 🚀 Choose Pipeline as the job type-->Add your pipeline script for  commit signoff in the pipeline configuration...>Click on Save to store the configuration.

![Screenshot from 2024-10-16 02-50-57](https://github.com/user-attachments/assets/d7b9ecd4-4917-4a96-9b2e-88cb0e93a2fa)

### 4. 🚀 Then Click on build to run the pipeline to perform commit signoff



### 5. 🚀 Now we are able to see build complete.
![Screenshot from 2024-10-20 02-39-18](https://github.com/user-attachments/assets/c46f27bc-c391-480d-9943-3e2970bdfb5e)




### 6. 🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-20 02-39-57](https://github.com/user-attachments/assets/2e5065cf-55e5-4cde-b63f-c94c9d886739)

![Screenshot from 2024-10-20 02-40-04](https://github.com/user-attachments/assets/9cf9aca1-3380-4976-948a-be51261129ad)


### 7. 🚀 Review the results of the dependency scanning in the console output.



### Shared Library structure

https://github.com/mygurukulam-p10/jenkins-shared-library.git

---

## Jenkinsfile
```
def call(String recipientEmail, String repoURL, String branchName) {
    try {
        // Get the last commit message
        def lastCommitMessage = sh(script: 'git log -1 --pretty=%B', returnStdout: true).trim()

        // Check if the commit contains "Signed-off-by:"
        if (!lastCommitMessage.contains("Signed-off-by:")) {
            currentBuild.result = 'FAILURE'
            error("Commit is not signed off. Please sign off your commit.")
        } else {
            echo "Commit is signed off."
        }
    } catch (Exception e) {
        // Mark build as failure in case of any exception
        currentBuild.result = 'FAILURE'
        echo "An error occurred: ${e.message}"
    } finally {
        // Prepare email subject based on build result
        def emailSubject = "Build Status: ${currentBuild.result} - Job ${env.JOB_NAME} [${env.BUILD_NUMBER}]"
        
        // Prepare email body with dynamic content
        def emailBody = """The current build result is: ${currentBuild.result}
                        Branch: ${branchName}
                        Repository: ${repoURL}
                        Build Number: ${env.BUILD_NUMBER}
                        ${currentBuild.result == 'FAILURE' ? "Error Message: ${e?.message ?: 'N/A'}" : "Build was successful!"}"""

        // Send email notification
        emailext(
            to: recipientEmail,
            subject: emailSubject,
            body: emailBody
        )
    }
}


```


