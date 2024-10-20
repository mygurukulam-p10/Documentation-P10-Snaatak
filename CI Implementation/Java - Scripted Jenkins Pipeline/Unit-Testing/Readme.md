
# Scripted Pipeline For Java Unit Testing

---



| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Brij Singh     | 09-10-2024  | Version 1.2  | Brij Singh          | 15-10-2024     |      Shikha Tripathi / Aakash Tripathi	 /Shreya Jaiswal	         |  Pramod Rajput / Shashi              |  Ashwani |
---

## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Unit Testing](#-steps-to-configuration-for-unit-testing)
5. [Jenskinfile](#jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction
This document provides an overview of implementing unit testing in a Go project using a Jenkins scripted pipeline. The aim is to ensure that the Go code is tested effectively, helping to identify bugs and ensure code quality.

## ⚙️ Pre-requisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**          | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Java 17**               | Required for compiling Jenkins and Spring Boot projects            |
| **✔️ Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access. |
|**✔️ Maven(3.6.9)**|Handles build automation and dependency management|
|**✔️ Junit (4.12)**|Facilitates Unit testing|

[Java CI Checks: Unit Testing detilas Document](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Application%20CI%20Design/Java%20CI%20checks/Unit%20Testing/Detailed%20Doc/readme.md)

---

## 🔍 System Requirements

### [Hardware System Requirements](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Unit%20Testing/readme.md)


---

## 💥 Steps to Configuration for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
**-->** Enter a name for your job (e.g., `Unit Testing`).

![image](https://github.com/user-attachments/assets/e388d316-a672-44cf-821e-7fed3f91bfd5)


### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![image](https://github.com/user-attachments/assets/d2f8884e-de9a-4056-a54d-801718257f82)


### 4. 🚀 Choose **Pipeline** as the job type. 
**-->** Add your pipeline script for unit testing in the pipeline configuration... 
**-->** Click on **Save** to store the configuration.
![image](https://github.com/user-attachments/assets/e0c0d9d0-f0d1-4986-af37-e1f990d4e7ce)


![image](https://github.com/user-attachments/assets/659fea5d-e591-4caa-9393-0d7f08e56385)


### 5. 🚀 Click on **Build** to run the pipeline for unit testing.
![image](https://github.com/user-attachments/assets/29acad30-12a6-4a9a-858e-11c70e5f089e)


### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-05 16-46-45](https://github.com/user-attachments/assets/56ead5a2-e956-4aba-8643-48c91018c420)

### 7. 🚀 Click on **Console Output** to see the complete build results.
![image](https://github.com/user-attachments/assets/d3cdeae2-1ae1-4f2f-9f02-17d0d75378fb)
![image](https://github.com/user-attachments/assets/711ffc99-b1e5-4b92-8763-57020abe64f8)



### 8. 🚀 Review the results of the unit testing process in the console output.
![Screenshot from 2024-10-05 16-47-23](https://github.com/user-attachments/assets/bc3a7d99-0190-4390-8480-ce501a7fafc4)

# Jenskinfile

```node {
         // Define tools
         def mvnHome = tool 'mvn'
     
         // Checkout stage
         stage('Checkout') {
             git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/salary-api.git'
         }
     
         // Test stage
         stage('Test') {
             echo "Executing Java Unit Testing"
             sh "${mvnHome}/bin/mvn test"
         }
     }

```

## 📛 Conclusion
This pipeline will check out your source code, build the project using Maven, and run JUnit tests.

## 📧 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| BrijSingh | brij.Singh.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                       |
|-------------------------|-------------------------------------|
| Jenkins Pipeline             | [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/)) |


