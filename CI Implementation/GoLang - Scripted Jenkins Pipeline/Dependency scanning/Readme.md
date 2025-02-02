# Dependency Scanning - Jenkins Pipeline

---


| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 28-10-2024         |     Tapan       |     Akshay Jain        |         
---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Dependency Scanning](#-steps-to-configuration-dependency-scanning)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of implementing dependency scanning in a project using snyk in a Jenkins scripted pipeline.


---
## ⚙️ Prerequisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**        | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Snyk CLI**       | Snyk CLI must be installed on the Jenkins server.                           |
| **✔️ Git**            | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**| Add your GitHub credentials (e.g., git-token) in Jenkins for repository access. |
| **✔️ Snyk API Token** | Add your Snyk API token in Jenkins to authenticate Snyk scans.              |

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |


# Snyk Plugin Installation and Configuration for Jenkins

## Steps to Install and Configure the Snyk Plugin

### 1. Install the Snyk Plugin:
- Navigate to **Jenkins Dashboard > Manage Jenkins > Manage Plugins**.
- Under the **Available** tab, search for **Snyk Security**.
- Install the **Snyk Security** plugin.
![Screenshot from 2024-10-12 01-58-44](https://github.com/user-attachments/assets/76ff563d-ec51-45c7-bf59-b87bb2534d48)


### 2. Configure the Snyk Plugin:
- After installing the plugin, go to **Jenkins Dashboard > Manage Jenkins > Configure System**.
- Scroll down to the **Snyk** section.
- Enter your **Snyk API Token** (you can generate it from your Snyk account under **Account Settings**).
- Click **Save** to apply the changes.

- ![Screenshot from 2024-10-12 02-36-07](https://github.com/user-attachments/assets/95268ff4-1a89-4773-b3a7-11104847f05e)


### 3. Configure Snyk Tool in Jenkins:
- Navigate to **Jenkins Dashboard > Manage Jenkins > Global Tool Configuration**.
- Under the **Snyk** section, click **Add Snyk**.
- Provide a name for the tool (e.g., `Snyk`).
- Specify the installation method (manual or automatic).
  - For **automatic installation**, Jenkins will download Snyk automatically.
  ![Screenshot from 2024-10-12 02-08-17](https://github.com/user-attachments/assets/2287c7c1-3d5b-44cf-a3ad-bec3f77d39a1)



# Steps to Configure Dependency Scanning in Jenkins

### 1. 🚀 Open Your Jenkins Dashboard
- Access your Jenkins dashboard by entering the Jenkins URL in your browser.

### 2. 🚀 Create a New Job
- Click on **New Item** in the Jenkins dashboard.
- Enter a name for your job (e.g., `Dependency Scanning`).
- Choose **Pipeline** as the job type.

![Creating a New Item](https://github.com/user-attachments/assets/664e5b1c-81ea-47dc-a7f3-44880f853b40)

### 3. 🚀 Provide a Job Description
- In the configuration page, provide a detailed description explaining what the pipeline will perform, such as dependency scanning and its benefits for securing the project.

![Adding a Job Description](https://github.com/user-attachments/assets/d35d2e13-a140-46e2-bb24-ae3a2268def2)

### 4. 🚀 Configure the Pipeline Script
- In the **Pipeline** section of the job, add your dependency scanning pipeline script.
- This script will automate the process of scanning for vulnerable dependencies in the project.
- Once done, click **Save** to store the pipeline configuration.

![Pipeline Script Configuration](https://github.com/user-attachments/assets/0602c080-537d-4675-81c7-5cc9c24f4f86)

![Save Pipeline Configuration](https://github.com/user-attachments/assets/8c724263-7ad3-4d78-ae9b-9f6461d74a64)

### 5. 🚀 Build the Pipeline
- After saving the configuration, click **Build Now** to trigger the pipeline and run the dependency scanning process.

![Trigger Build](https://github.com/user-attachments/assets/8955da9b-ed8d-4a08-a7a8-6f1f487cecc3)

### 6. 🚀 View Build Completion
- Once the build completes, you’ll see a **Success** message or the current status of the build on the dashboard.

![Build Complete](https://github.com/user-attachments/assets/bd6d95a5-ea96-497e-9da4-7b6cbfd12283)

### 7. 🚀 Review the Console Output
- Click on **Console Output** to view the complete details of the build, including the output of the dependency scanning process.

![View Console Output](https://github.com/user-attachments/assets/b8f4fc28-b689-4417-8abb-12bfddf9c2b5)

### 8. 🚀 Review Dependency Scan Results
- Review the results of the dependency scan in the console output. It will highlight any vulnerable dependencies detected during the scan, which should be fixed promptly.

![Review Results](https://github.com/user-attachments/assets/a654dad5-91c5-41f2-9586-d26f8fee96f6)

### 9. 🚀 Send Build Report via Email
![Screenshot from 2024-10-21 18-17-52](https://github.com/user-attachments/assets/c33fe364-72ac-418e-a433-3462548be8c5)


# Jenkinsfile
```

properties([
    parameters([
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from'),
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL'),
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository'),
        string(name: 'SNYK_TOKEN', defaultValue: '', description: 'Snyk API token for authentication'),
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
    ])
])

node {
    // Set up Go and Snyk tool paths
    def goTool = tool name: 'golang', type: 'go'
    env.PATH = "${goTool}/bin:${env.PATH}"

    try {
        stage('Clone Repository') {
            // Clone the specified repository from GitHub using parameters
            git branch: params.BRANCH_NAME, url: params.REPO_URL, credentialsId: params.CREDENTIALS_ID
        }

        stage('Run Snyk Test') {
            // Run Snyk test command to generate the report
            script {
                snykSecurity(
                    snykInstallation: 'snyk',
                    snykTokenId: params.SNYK_TOKEN
                )
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
                    Build Number: ${env.BUILD_NUMBER}
                    """
        )
    }
}

```
[Dependency Scanning Jenkinsfile](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Golang-scripted-pipeline/Dependency-scanning/Jenkinsfile)


## 🏁 Conclusion
The dependency scanning stage successfully analyzes the project's dependencies, identifying any known vulnerabilities and providing a report to ensure the application is secure.

## 📞 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Snyk Documentation       | [Snyk Documentation](https://docs.snyk.io/)             |
| Snyk CLI Usage           | [Snyk CLI Documentation](https://docs.snyk.io/snyk-cli) |
| Jenkins Pipeline         | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
