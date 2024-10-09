# ☕ Java Code Compilation with Scripted Jenkins Pipeline

| ✍️ Author      | 📅 Created on  | 📌 Version  | 📝 Last updated by | 📅 Last edited on  |
|----------------|----------------|------------|--------------------|--------------------|
|Brij Singh   | 03-10-2024     | Version 1  | Brij Singh       | 09-10-2024         |

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

**6. 🚀 Console Output**
After the build is complete, check the console output for logs and any issues encountered during the pipeline execution.

***📛 Conclusion***
By following this guide, you've successfully created a Scripted Jenkins Pipeline for Java code compilation. Regular builds and testing using Maven ensures continuous integration, allowing early detection of issues. Integrate this scripted pipeline into your CI/CD workflow for optimal performance.



***📚 References***
|🔗 Links	|📄 Descriptions|
|Build a Java app with Maven	Jenkins Tutorial on Maven Builds
Apache Maven Documentation	Official Apache Maven Documentation

