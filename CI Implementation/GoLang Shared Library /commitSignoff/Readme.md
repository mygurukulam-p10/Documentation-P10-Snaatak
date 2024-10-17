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

### 1. 🚀 Open your Jenkins Dashboard.

### Step 1.1: Configure the Shared Library in Jenkins

1. Go to the **Jenkins Dashboard**.
2. Click on **Manage Jenkins** → **Configure System**.
3. Scroll down to **Global Pipeline Libraries** and click **Add**.
4. Fill out the details:
   - **Name**: Give your shared library a name (e.g., `shared-library`).
   - **Default Version**: (Optional) Enter the branch, tag, or commit hash (e.g., `main`).
   - **Retrieval Method**: Choose `Modern SCM` and select **Git**.
   - **Repository URL**: Provide the URL to the shared library repository.
   - **Credentials**: Select or add the necessary credentials.

5. Click **Save**.

### 2. 🚀 Create a New Jenkins Job

- Navigate to **New Item** and enter a name for your job (e.g., `Commit Sign-Off Pipeline with Email`).
- Choose **Pipeline** as the job type.
- Add the parameterized pipeline script (below) to check commit sign-off and send email notifications on failure.

---

## Jenkinsfile

This pipeline does the following:
1. Checks if commits are signed off.
2. Sends an email if commits are missing a sign-off.
3. Allows the Git branch and recipient email to be parameterized.

```groovy
@Library("shared1") _
pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to check for commit sign-off')
        string(name: 'EMAIL_RECIPIENT', defaultValue: 'you@example.com', description: 'Email address for notifications')
    }

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    def branch = params.BRANCH_NAME
                    def creds = 'amit_cred'
                    def url = 'git@github.com:mygurukulam-p10/employee-api.git'
                    echo "Checking out branch: ${branch} from URL: ${url} using credentials ID: ${creds}"
                    gitCheckout(branch, creds, url)
                }
            }
        }

        stage('Validate Commit Sign-Off') {
            steps {
                script {
                    def result = sh(script: "git log --format='%H %s' | grep -v 'Signed-off-by'", returnStatus: true)
                    if (result != 0) {
                        echo "Some commits are missing 'Signed-off-by'. Sending email notification."
                        currentBuild.result = 'FAILURE'
                        sendFailureEmail(params.EMAIL_RECIPIENT)
                        error "Commit sign-off validation failed. Check the commit messages."
                    } else {
                        echo "All commits are properly signed off."
                    }
                }
            }
        }
    }

    post {
        failure {
            script {
                echo "Build failed due to commit sign-off issues."
            }
        }
    }
}

