![Uploading 23W11-blog-HowToHandleSecretsWithJenkins.png…]()



# 🐞 Scripted Pipeline: Credential Scanning

| ✍️ **Author**      | 📅 **Created on**  | 📌 **Version**    | 📝 **Last updated by** | 📅 **Last edited on** |
|-------------------|--------------------|-------------------|-----------------------|-----------------------|
| Brij Singh      | 09-10-2024          | Version 1         | Brij Singh            | 09-10-2024            |
---

## 📑 Table of Contents
1. [Introduction](#introduction)
2. [Why Scripted Pipeline](#why-scripted-pipeline)
3. [Flow Diagram](#flow-diagram)
4. [Pre-requisites](#pre-requisites)
5. [Setup of Credential Scanning](#setup-of-credential-scanning)
6. [Jenkinsfile](#jenkinsfile)
7. [Conclusion](#conclusion)
8. [Contact Information](#contact-information)
9. [Resources and References](#resources-and-references)

---

## 📖 Introduction
Scripted Pipelines in Jenkins let you create CI/CD pipelines using Groovy. This method offers flexibility for complex workflows, allowing you to write scripts that run step-by-step with full access to Jenkins APIs for advanced automation.

### 🔐 Credential Scanning Tool Used: GitLeaks
[GitLeaks](https://github.com/gitleaks/gitleaks) is a powerful open-source tool designed to scan Git repositories for sensitive information such as credentials, API keys, and passwords. It ensures that confidential data is not accidentally leaked in version-controlled codebases.

---

## ❓ Why Scripted Pipeline

| ⚙️ **Aspect**                  | 📝 **Description**                                                                                                                                                  |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **📜 Imperative Syntax**        | Pipelines are written as Groovy scripts, providing full control over execution flow for complex logic and dynamic behavior.                                        |
| **🔄 Programmatic Constructs**  | Allows usage of loops, conditions, variables, and functions for building highly customizable pipelines.                                                            |
| **🔧 Direct Access to APIs**    | Scripts can directly interact with Jenkins APIs for fine-grained automation and integration with external systems or plugins.                                      |
| **🔗 Extensibility**            | Enables defining custom functions and importing external libraries to enhance pipeline functionality and reusability.                                             |
| **🧰 Legacy Support**           | Widely adopted in environments with existing pipelines, offering familiarity and backward compatibility with legacy systems.                                      |
| **🎓 Learning Curve**           | Requires knowledge of Groovy syntax and Jenkins pipeline concepts, leading to a steeper learning curve, especially for newcomers.                                  |
| **🛠 Debugging and Maintenance**| The imperative approach can make debugging and maintenance more challenging, necessitating proper organization, documentation, and testing.                       |

---


---

## 🛠 Pre-requisites

| **Tool**   | **Version**  |
|------------|--------------|
| **🖥️ Jenkins**  | 2.426.3    |
| **🔍 Gitleaks** | 8.18.2     |

---

## 🔧 Setup of Credential Scanning

💥 Steps to Configuration Declarative pipelines for cred scanning

1. 🚀 Open your Jenkins Dashboard.

![image](https://github.com/user-attachments/assets/07f44dd1-f056-428a-87da-eaf75218abe9)

2. 🚀 Click on New Item.** ---> **Enter a name for your job (e.g., cred-scanning).

![image](https://github.com/user-attachments/assets/23917a60-7ee6-47a1-ac3f-3088fa61e3aa)

3. 🚀 Provide a description for the pipeline that performs credential scanning.

![image](https://github.com/user-attachments/assets/35046bd5-5d40-4daf-9df9-70e287bfb3d0)

4. Create the repo for add jenkinfile which will be using in pipeline script for SCM

![image](https://github.com/user-attachments/assets/02401704-3722-48c5-8f02-c6388cf6aa36)

![image](https://github.com/user-attachments/assets/40ec69e4-81fc-4069-b5d9-747a1c704b29)

5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.

![image](https://github.com/user-attachments/assets/d3ed2a70-6782-4399-a006-f65170057721)
 
![image](https://github.com/user-attachments/assets/d5ceb3aa-ad9a-4632-832d-a6f31cdff771)

6. 🚀 Then Click on build to run the pipeline to perform
 





🔚 Conclusion
Scripted Pipelines in Jenkins allow you to define pipelines using Groovy code, giving you more control over each step. It's ideal for cases where you need detailed customization and advanced automation features. However, since you're writing code, it can be more challenging to learn, troubleshoot, and maintain compared to Declarative Pipelines, which are easier to set up but less flexible.

## 📧 Contact Information

| 👨‍💻 **Name**   | 📧 **Email Address**                                  |
|-----------------|-------------------------------------------------------|
| Brij Singh       | [Brij.singh.snaatak@mygurukulam.co](mailto:brij.singh.snaatak@mygurukulam.co) |

---

📚 Resources and References

Credential Scanning POC Steps	[Link](https://medium.com/@srianis/credential-scanning-tool-detect-secrets-installation-and-usage-4afeb2be50c4)

