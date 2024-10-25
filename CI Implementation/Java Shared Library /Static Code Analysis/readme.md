
# Static Code Analysis for Java - Shared Library 
![image](https://github.com/user-attachments/assets/2093140b-3a93-4fc7-a620-e3ef6855b672)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|-------------|------------|-----------------|----------------|------------|-----------------|----------------|
| Vinay Bansal| 14-10-2024  | Version 4  | Vinay Bansal    | 25-10-2024     |Shreya Jaiswal|||

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration to Static Code Analysis](#-steps-to-configuration-to-static-code-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Shared Library for Bugs analysis in Java. Jenkins, as a popular automation server, supports a variety of build configurations. Static code analysis is the process of examining source code without executing it to identify potential issues, improve quality.


---

## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **Tools for Static Code Analysis** [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Static%20Code%20Analysis%20Doc).

## 🔍 System Requirements [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Static%20code%20analysis/readme.md#-system-requirements)


---

## 💥 Steps to Configuration to Static Code Analysis
### Understand Shared Library Syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/CI%20Implementation/Java%20Shared%20Library%20/%20Bugs%20analysis#understand-shared-library-syntax)


### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
![image](https://github.com/user-attachments/assets/00daf044-f056-4c4c-8464-0d62828ea964)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![image](https://github.com/user-attachments/assets/abb8011a-de5d-41ec-a64c-467f3baa768f)



### 4. 🚀 Create the repo for add vars file which will be using in pipeline script.
```
def call() {
    // Set environment variables at the top level
    environment {
        JAVA_HOME = '/usr/lib/jvm/java-11-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:${PATH}"
    }

    def GIT_USER_EMAIL = 'vinay.bansal.snaatak@mygurukulam.co'
    def recipientEmail = GIT_USER_EMAIL
    def buildStatus = currentBuild.result ?: 'SUCCESS' // Default to SUCCESS if not set
    def checkstyleReportFile = 'checkstyle-report.html' // File to store Checkstyle output

    stage('Set Environment Variables') {
        // Validate JAVA_HOME is set correctly
        sh 'echo $JAVA_HOME'
        sh 'java -version'
    }

    stage('Clone Repository') {
        // Clone the Git repository using SSH key
        git branch: 'main', 
            url: 'git@github.com:mygurukulam-p10/salary-api.git', 
            credentialsId: 'new-key'
    }     

    stage('Analyze Code') {
        // Navigate to the directory where pom.xml is located
        dir('/var/lib/jenkins/workspace/Java_staticCode') {
            // List files for debugging purposes
            sh 'ls -R'

            // Run Maven checkstyle to analyze code and capture output
            sh 'mvn checkstyle:checkstyle -Dproject.build.directory=/var/lib/jenkins/workspace/Java_staticCode/target -Dformat=ALL'
            archiveArtifacts artifacts: "**/${checkstyleReportFile}", allowEmptyArchive: true
        }
    }

    stage('Notify') {
        // Send email notification
        emailext(
            to: recipientEmail,
            subject: "Jenkins Build ${buildStatus}: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: """
                Build Result: ${buildStatus}
                Job Name: ${env.JOB_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Checkstyle Report: ${checkstyleReportFile}
            """,
            attachLog: true,
            attachmentsPattern: "**/${checkstyleReportFile}"
        )
        
        echo "Notification sent to ${recipientEmail} for build status: ${buildStatus}"
    }
}
```
![image](https://github.com/user-attachments/assets/51dec8aa-f7d0-444a-8189-f5c390e71388)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code Analysis in the pipeline script ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/add97a5e-cfbc-4516-8dcc-08c80ef3a086)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/ade343d1-6ace-4c3c-b961-e1f411bffc13)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/98bd7d8c-99f9-41e6-8344-87fe8a4b45da)

![image](https://github.com/user-attachments/assets/05ffdfee-da3a-49b3-94b8-c32a899f6cac)


### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/2389b841-b24f-4880-8fa6-39c302aa7aff)

### 10.🚀 Verify Report.
![image](https://github.com/user-attachments/assets/47b1aade-6af7-47c9-84b3-6ee74055f9d4)

### 9.🚀 Verify Email.
![image](https://github.com/user-attachments/assets/08a49ef2-e73f-49ad-859e-b26c5d4b345c)


## 📛 Conclusion
We run Checkstyle command and found 88 Checkstyle violations. This means there are parts of the code that don't follow our coding standards. These issues can make the code harder to read and maintain.

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Static%20Code%20Analysis%20Doc|DOC|
|https://tinyurl.com/mrxmx9wy|(POC): Static Code Analysis|

