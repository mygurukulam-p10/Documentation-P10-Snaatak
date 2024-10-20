# Commit-Signed off- Scripted Jenkins Pipeline  
![image](https://github.com/user-attachments/assets/80a75bdc-d164-43de-946b-e0bed04067c6)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal| 11-10-2024  | Version 1  | Vinay Bansal    | 12-10-2024     |

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
|AWS Credentials |Access key ID and Secret access key|


---

## 💥 Steps to Configuration Scripted pipelines for Commit Signed Off

### 1. 🚀 Open your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/8388e339-d07b-4acd-9e65-c52935634788)


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Commit-Signed Off`).
![2](https://github.com/user-attachments/assets/f84d7dd1-d975-4f15-b782-40e1745dc640)

### 3. 🚀 Provide a description for the pipeline that performs Commit-Signed off.
![3](https://github.com/user-attachments/assets/5694abe0-8dbc-4902-b7ec-c7c424d29158)


### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM
![image](https://github.com/user-attachments/assets/df7d0e73-c1ad-4045-a9e3-a4df3ab2e29f)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Commit-Signed off in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/a0255aaa-9d71-4871-ba34-3969dad5dd5a)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/bbad46f7-4bcb-4f80-8ff0-129cfd7cfeb5)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/fe73aea4-7697-4098-aa01-f5ff8f779572)
![image](https://github.com/user-attachments/assets/c60289ad-7481-41e8-b09f-f45de86c68e3)

### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/aee537c3-7b1c-42b2-a9fd-3002bc18b89f)


---

## 📛 Conclusion
This Jenkins pipeline streamlines the process of ensuring that all commits are properly signed off, enhancing code quality and compliance. 
By automating the verification and amendment of commit messages,it fosters a more responsible and accountable development workflow.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://stackoverflow.com/questions/69182492/you-only-have-one-commit-incorrectly-signed-off| **Stackoverflow** |
