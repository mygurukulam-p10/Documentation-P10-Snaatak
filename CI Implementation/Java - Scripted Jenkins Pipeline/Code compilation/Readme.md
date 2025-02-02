# ☕ Java Code Compilation with Scripted Jenkins Pipeline

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Brij Singh     | 09-10-2024  | Version 1.2  | Brij Singh          | 15-10-2024     |      Shikha Tripathi / Aakash Tripathi	 /Shreya Jaiswal	         |  Pramod Rajput / Shashi              |  Ashwani |

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

[Hardware Specifications](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md)

---

## 🛠️ Steps to Configure Scripted Pipelines for Code Compilation

### 1. 🚀 **Open Jenkins Dashboard**
1. Go to the Jenkins dashboard.

2.Configure Maven tool in Jenkins
![image](https://github.com/user-attachments/assets/d7acd158-96c9-4057-bc1b-f127126896cf)

3. Click on **New Item**.
![image](https://github.com/user-attachments/assets/942061a3-4727-4f5c-83ce-4155ee08b2cb)


4. Name the job (e.g., `code-compilation-scripted`).
![image](https://github.com/user-attachments/assets/09b4950f-bb5b-47c8-967e-bba9c2c041e3)

5.Provide a description for the pipeline that performs code-compilation.
![image](https://github.com/user-attachments/assets/496bbc72-0fbc-4a28-847f-3d14970c52db)

6. In the "Pipeline" section, switch to "Pipeline script From SCM" and enter your scripted pipeline.
![image](https://github.com/user-attachments/assets/0a4eaff5-fa47-45ef-b137-2765ecc78ee6)

7. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/1473d05e-c051-4665-840a-223702287f09)

8. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/7fb98be3-a6d6-4839-9c2c-02132d4d1b72)





***4. 🚀 Configure SCM***
In the "Pipeline" section, configure the SCM settings with your Git repository URL and Jenkins credentials.

![image](https://github.com/user-attachments/assets/f1bf7adf-6e94-4ad5-936b-ab7d1ae4e829)

**5. 🚀 Run the Build**
Click Build Now to start the pipeline. You can monitor the build status and review the output in the Console.
![image](https://github.com/user-attachments/assets/bf14cdfd-8089-47bf-88af-4cb07f1219b1)

![image](https://github.com/user-attachments/assets/01e8a112-281f-49f3-8f37-1f79131ad986)


**6. 🚀 Console Output**
After the build is complete, check the console output for logs and any issues encountered during the pipeline execution.
![image](https://github.com/user-attachments/assets/1fad35a7-a1ba-4515-a111-ce06c68ec9a6)

![image](https://github.com/user-attachments/assets/c154bece-cb2b-4ec9-b782-7151f6bcc926)




***📛 Conclusion***
By following this guide, you've successfully created a Scripted Jenkins Pipeline for Java code compilation. Regular builds and testing using Maven ensures continuous integration, allowing early detection of issues. Integrate this scripted pipeline into your CI/CD workflow for optimal performance.

## 📧 Contact Information

| 👨‍💻 **Name**   | 📧 **Email Address**                                  |
|-----------------|-------------------------------------------------------|
| Brij Singh       | [Brij.singh.snaatak@mygurukulam.co](mailto:brij.singh.snaatak@mygurukulam.co) |


## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/|Build a Java app with Maven |
|https://tinyurl.com/su8ennjz|(POC): code-compilation |
|[Code compilation](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Code%20compilation/readme.md)| Declarative Jenkins Pipeline
