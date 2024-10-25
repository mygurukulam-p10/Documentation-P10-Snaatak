
# Java - Declarative Jenkins Pipeline for Dependency scanning


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 05-10-2024  | Version 1  | Vinay Bansal    | 11-10-2024   |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Dependency scanning](#-steps-to-configuration-declarative-pipelines-for-dependency-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline for Dependency scanning. Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Java**: Required to run the built Java application.
3. **Maven**: Simplifies build management
4. **OWASP Dependency-Check**:	A software composition analysis tool that identifies project dependencies and checks for known vulnerabilities.

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

![image](https://github.com/user-attachments/assets/ea005028-b68b-4a44-9e5f-b61b01802948)

## 💥 Steps to Configuration Declarative pipelines for Dependency scanning
### Understand Declarative Pipeline syntax [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md#understand-declarative-pipeline-syntax)

### To enable the OWASP Dependency-Check plugin in your Maven project, add the following configuration to your pom.xml file. Ensure this configuration is placed within the <build> section
```
            <!-- Add the OWASP Dependency-Check plugin -->
            <plugin>
                <groupId>org.owasp</groupId>
                <artifactId>dependency-check-maven</artifactId>
                <version>10.0.4</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```

### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency scanning`).
![2](https://github.com/user-attachments/assets/7449f5ee-c0f5-4afd-968d-127b7fbdce94)

### 3. 🚀 Provide a description for the pipeline that performs Dependency scanning.
![3](https://github.com/user-attachments/assets/81e1e782-18f7-45e2-a440-822cd273b048)

### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
```
pipeline {
    agent any
    environment {
        recipientEmail = 'vinay.bansal.snaatak@mygurukulam.co' // Set the recipient email as an environment variable
    }
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'git@github.com:mygurukulam-p10/salary-api.git', credentialsId: 'new-key'
            }
        }
        stage('Build and Run Tests') {
            steps {
                dir('/var/lib/jenkins/workspace/Dependency-scanning') {
                    // List files for debugging
                    sh 'ls -R'
                }
            }
        }
        stage('OWASP Dependency Check') {
            steps {
                script {
                    try {
                        // Log the contents of the target directory
                        dir('/var/lib/jenkins/workspace/Dependency-scanning/target') {
                            sh 'ls -R'
                        }

                        // Run the Dependency Check
                        sh 'mvn dependency-check:check -Dproject.build.directory=/var/lib/jenkins/workspace/Dependency-scanning/target -Dformat=ALL'
                    } catch (Exception e) {
                        echo 'DP check Failed!'
                    }
                }
            }
        }
    }

    post {
        always {
            // Archive the dependency check report
            archiveArtifacts artifacts: '**/dependency-check-report.html'
            sh "ls ${WORKSPACE}"
            echo 'DP check completed!'
            sh 'tree ${WORKSPACE}'
        }
        success {
            // Send email notification for success with attachment
            emailext(
                to: recipientEmail,
                subject: "Jenkins Build Success: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: """
                    Build Result: SUCCESS
                    Job Name: ${env.JOB_NAME}
                    Build Number: ${env.BUILD_NUMBER}
                """,
                attachLog: true,
                attachmentsPattern: '**/dependency-check-report.html'
            )
            echo "Notification sent to ${recipientEmail} for build status: SUCCESS"
        }
        failure {
            // Send email notification for failure with attachment
            emailext(
                to: recipientEmail,
                subject: "Jenkins Build Failure: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
                body: """
                    Build Result: FAILURE
                    Job Name: ${env.JOB_NAME}
                    Build Number: ${env.BUILD_NUMBER}
                """,
                attachLog: true,
                attachmentsPattern: '**/dependency-check-report.html'
            )
            echo "Notification sent to ${recipientEmail} for build status: FAILURE"
        }
    }
}
```
![image](https://github.com/user-attachments/assets/d5682ace-a06a-43d6-81af-9535477a4293)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for DAST in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/38cf7790-6d5e-4988-a151-7a162b9a4356)
![image](https://github.com/user-attachments/assets/9617bf02-b6bd-487c-b2dd-600eba4ca804)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/e13df9b3-05dd-45bd-b831-a1c9c55f8a55)



### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/f2062413-b99b-44a4-a676-3ee5f6641ccd)

![image](https://github.com/user-attachments/assets/395dc2f8-c635-4c15-9256-67ae4c80f8fe)

![image](https://github.com/user-attachments/assets/8bea5079-6c95-4a2d-98cb-0f15fc545a01)






### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/44ff86fa-a711-403f-b7e5-d00bdbf8604f)

### 10.🚀 Verification.
![image](https://github.com/user-attachments/assets/7679e89a-5978-4c84-827b-617de10d4e86)


## 📛 Conclusion
In conclusion, integrating OWASP Dependency-Check into your development process offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies. By regularly scanning and analyzing your project dependencies, you can stay ahead of known vulnerabilities, ensuring the overall security and reliability of your software applications

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://owasp.org/|OWASP Overview|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Java%20CI%20checks/Dependency%20scanning%20POC|(POC): Dependency scanning|
