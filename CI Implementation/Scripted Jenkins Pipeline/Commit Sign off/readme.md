# Commit-Signed off- Scripted Jenkins Pipeline  
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal| 10-10-2024  | Version 1  | Vinay Bansal    | 10-10-2024     |

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

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Commit-Signed Off`).

### 3. 🚀 Provide a description for the pipeline that performs Commit-Signed off.


### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Commit-Signed off in the pipeline script for SCM ...> add repo link & credintial, file path.


### 6. 🚀 Then Click on build to run the pipeline to perform

### 7.🚀 Now we are able to see build complete-


### 8.🚀 Click on Console Output to see the complete build.

### 9.🚀 Review the stages of the build process in the console output.


---

## 📛 Conclusion
This Jenkins pipeline streamlines the process of ensuring that all commits are properly signed off, enhancing code quality and compliance. 
By automating the verification and amendment of commit messages,it fosters a more responsible and accountable development workflow.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://stackoverflow.com/questions/69182492/you-only-have-one-commit-incorrectly-signed-off| **Stackoverflow** |
|https://github.com/microsoft/vscode/issues/47395| **Repo-brettjacobson** |
