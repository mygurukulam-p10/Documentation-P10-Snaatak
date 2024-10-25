# Commit-Signed off- Scripted Jenkins Pipeline  
![image](https://github.com/user-attachments/assets/80a75bdc-d164-43de-946b-e0bed04067c6)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|-------------|------------|-----------------|----------------|------------|-----------------|----------------|
| Vinay Bansal| 11-10-2024  | Version 4  | Vinay Bansal    | 25-10-2024     |Shreya Jaiswal|||

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Scripted pipelines for Commit Signed Off](#-steps-to-conguration-scripted-pipelines-for-commit-signed-off)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This Readme file implements a Jenkins pipeline that ensures every commit in the repository is accompanied by a valid Signed-off-by message. It automates the verification process, checking the latest commit and amending it if necessary. With a defined user name and email,
it maintains accountability in the development workflow. This pipeline enhances code integrity and compliance with contribution standards.

---

## ⚙️ Pre-requisites

| Requirement          | Description                                               |
|---------------------|-----------------------------------------------------------|
| Git                 | Ensure Git is installed on your system.                  |
| Jenkins             | Set up Jenkins for CI/CD integration.                     |
| GitHub Repository    | Access to a GitHub repository for version control.        |
| User Credentials    | Git user name and email should be configured globally.    |


---

## 💥 Steps to Configuration Scripted pipelines for Commit Signed Off

### 1. 🚀 Open your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/8388e339-d07b-4acd-9e65-c52935634788)


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Commit-Signed Off`).
![2](https://github.com/user-attachments/assets/f84d7dd1-d975-4f15-b782-40e1745dc640)

### 3. 🚀 Provide a description for the pipeline that performs Commit-Signed off.
![3](https://github.com/user-attachments/assets/5694abe0-8dbc-4902-b7ec-c7c424d29158)


### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
```
node {
    // Define Git user information
    def GIT_USER_NAME = 'Vinay Bansal'
    def GIT_USER_EMAIL = 'vinay.bansal.snaatak@mygurukulam.co'
    
    // Specify the recipient email for notifications
    def recipientEmail = GIT_USER_EMAIL

    // Capture current build status
    String buildStatus = currentBuild.currentResult ?: 'SUCCESS' 
    String authorName = '' // Variable to store the author's name

    try {
        stage('Checkout') {
            checkout scm
        }

        stage('Set Git Identity') {
            // Set the user name and email for Git
            sh "git config --global user.email '${GIT_USER_EMAIL}'"
            sh "git config --global user.name '${GIT_USER_NAME}'"
        }

        stage('Verify and Sign-off Latest Commit') {
            // Get the latest commit hash
            def commit = sh(script: "git rev-parse HEAD", returnStdout: true).trim()
            // Get the author name of the latest commit
            authorName = sh(script: "git log -1 --pretty=format:'%an'", returnStdout: true).trim()
            // Check for Signed-off-by in the latest commit message
            def signoff = sh(script: "git show --format='%B' ${commit} | grep -q 'Signed-off-by'", returnStatus: true)

            if (signoff != 0) {
                // Amend the latest commit to add the Signed-off-by line
                sh """
                git commit --amend --no-edit --signoff -m "\$(git log -1 --pretty=%B) Signed-off-by: ${GIT_USER_NAME} <${GIT_USER_EMAIL}>"
                """
            } else {
                echo "Latest commit ${commit} by ${authorName} already has a valid Signed-off-by by ${GIT_USER_NAME}."
            }
        }
    } catch (Exception e) {
        echo "Pipeline failed: ${e.message}"
        echo "Stacktrace: ${e.getStackTrace().toString()}"
        currentBuild.result = 'FAILURE'
    } finally {
        echo 'Pipeline completed.'
        if (currentBuild.result == 'SUCCESS') {
            echo "Pipeline succeeded. Verified by: ${GIT_USER_NAME}"
        }

        // Send email notification with author name included
        emailext(
            to: recipientEmail,
            subject: "Jenkins Build ${buildStatus}: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: """
                Build Result: ${buildStatus}
                Job Name: ${env.JOB_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Author of the Latest Commit: ${authorName}
            """,
            attachLog: true
        )

        echo "Notification sent to ${recipientEmail} for build status: ${buildStatus}"
    }
}
```
![image](https://github.com/user-attachments/assets/d7b888e7-4780-4b4c-8f19-004161e378d6)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Commit-Signed off in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/a0255aaa-9d71-4871-ba34-3969dad5dd5a)
![image](https://github.com/user-attachments/assets/f6e87a87-ddc1-41b9-9452-dbcb64d3b67d)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/bbad46f7-4bcb-4f80-8ff0-129cfd7cfeb5)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/fe73aea4-7697-4098-aa01-f5ff8f779572)
![image](https://github.com/user-attachments/assets/0b59f58e-d29f-43c5-8c31-17cd59bbb918)

### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/aee537c3-7b1c-42b2-a9fd-3002bc18b89f)

### 9.🚀 Email Verify
![image](https://github.com/user-attachments/assets/9ab4aad8-40d6-4da8-ab73-5467778f10ee)

---

## 📛 Conclusion
This Jenkins pipeline streamlines the process of ensuring that all commits are properly signed off, enhancing code quality and compliance. 
By automating the verification and amendment of commit messages,it fosters a more responsible and accountable development workflow.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://stackoverflow.com/questions/69182492/you-only-have-one-commit-incorrectly-signed-off| **Stackoverflow** |
