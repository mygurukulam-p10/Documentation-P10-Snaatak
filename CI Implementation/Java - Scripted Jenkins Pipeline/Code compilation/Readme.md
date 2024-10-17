# ☕ Java Code Compilation with Scripted Jenkins Pipeline

| ✍️ Author      | 📅 Created on  | 📌 Version  | 📝 Last updated by | 📅 Last edited on  |
|----------------|----------------|------------|--------------------|--------------------|
|Brij Singh   | 10-10-2024     | Version 2  | Brij Singh       | 09-10-2024         |

---

## 📚 Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [🛠️ Steps to Configure Scripted Pipelines for Code Compilation](#-steps-to-configure-scripted-pipelines-for-code-compilation)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---

## 💥 Introduction
This document provides steps to configure a **Scripted Jenkins Pipeline** for Java code compilation. Scripted Pipelines, written in Groovy, offer more flexibility compared to Declarative Pipelines, enabling the creation of complex workflows.

---
***Flow Diagram***

![Untitled-2024-10-18-0211](https://github.com/user-attachments/assets/913c4ae5-8898-4a40-9f87-0f1b29a82f54)


## ⚙ Pre-requisites
1. **Jenkins**: A Jenkins instance must be running.
2. **Java**: Required for Java application builds.
3. **Maven**: A build management tool for Java projects.

---

## 🔍 System Requirements
| 🖥️ Hardware Specifications | ⚙️ Minimum Requirement |
|----------------------------|------------------------|
| **Processor**               | Dual-core CPU          |
| **Memory**                  | 2 GB RAM               |
| **Disk Space**              | 10 GB                  |
| **Operating System**        | Ubuntu 22.04 LTS       |

---

## 🛠️ Steps to Configure Scripted Pipelines for Code Compilation

### 1. 🚀 **Open Jenkins Dashboard**
1. Go to the Jenkins dashboard.
2. Click on **New Item**.
![image](https://github.com/user-attachments/assets/942061a3-4727-4f5c-83ce-4155ee08b2cb)


3. Name the job (e.g., `code-compilation-scripted`).
![image](https://github.com/user-attachments/assets/09b4950f-bb5b-47c8-967e-bba9c2c041e3)

Provide a description for the pipeline that performs code-compilation.
![image](https://github.com/user-attachments/assets/496bbc72-0fbc-4a28-847f-3d14970c52db)

2. In the "Pipeline" section, switch to "Pipeline script From SCM" and enter your scripted pipeline.
![image](https://github.com/user-attachments/assets/0a4eaff5-fa47-45ef-b137-2765ecc78ee6)

3. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/1473d05e-c051-4665-840a-223702287f09)

4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/7fb98be3-a6d6-4839-9c2c-02132d4d1b72)



Explanation of the Stages:
Checkout: Clones your repository from a Git source.
Set Up Maven: Configures Maven for the build.
Build: Compiles the Java code.
Run Unit Tests: Runs unit tests to ensure the code is functional.
Package: Packages the compiled code into a JAR or WAR file.
Archive Artifacts: Archives the generated build artifacts.
Post-Build Cleanup: Cleans the workspace to avoid conflicts with future builds.

***4. 🚀 Configure SCM***
In the "Pipeline" section, configure the SCM settings with your Git repository URL and Jenkins credentials.

**5. 🚀 Run the Build**
Click Build Now to start the pipeline. You can monitor the build status and review the output in the Console.
![image](https://github.com/user-attachments/assets/bf14cdfd-8089-47bf-88af-4cb07f1219b1)


**6. 🚀 Console Output**
After the build is complete, check the console output for logs and any issues encountered during the pipeline execution.
![image](https://github.com/user-attachments/assets/1fad35a7-a1ba-4515-a111-ce06c68ec9a6)

![image](https://github.com/user-attachments/assets/c154bece-cb2b-4ec9-b782-7151f6bcc926)


***📛 Conclusion***
By following this guide, you've successfully created a Scripted Jenkins Pipeline for Java code compilation. Regular builds and testing using Maven ensures continuous integration, allowing early detection of issues. Integrate this scripted pipeline into your CI/CD workflow for optimal performance.



## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/|Build a Java app with Maven |
|https://tinyurl.com/su8ennjz|(POC): code-compilation |
