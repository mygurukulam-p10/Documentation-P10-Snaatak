# Commit-Signed off- Declarative Jenkins Pipeline  
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 10-10-2024  | Version 1  | Megha Tyagi     | 10-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Declarative pipelines for Commit Signed Off](#-steps-to-conguration-declarative-pipelines-for-commit-signed-off)
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

## 💥 Steps to Configuration Declarative pipelines for Commit Signed Off

### 1. 🚀 Open your Jenkins Dashboard.
<img width="951" alt="Screenshot 2024-10-03 171617" src="https://github.com/user-attachments/assets/e6448943-be68-4a6f-91d1-76e29d206a2f">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Commit-Signed Off`).
![Screenshot 2024-10-10 191142](https://github.com/user-attachments/assets/9c4ef408-88e8-4225-a31b-c84ab45da515)

### 3. 🚀 Provide a description for the pipeline that performs Commit-Signed off.
![Screenshot 2024-10-10 191201](https://github.com/user-attachments/assets/27115d33-8ef1-48e1-ab74-61b32ece1b93)


### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM
![Screenshot 2024-10-10 191411](https://github.com/user-attachments/assets/569c20eb-042f-4002-bf40-ed3710ac8ecd)
![Screenshot 2024-10-10 191428](https://github.com/user-attachments/assets/503ebc47-9464-45ca-aa7b-8b9f7425dd0f)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Commit-Signed off in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-10 191257](https://github.com/user-attachments/assets/9a22293e-eccf-46db-99d6-1fd1f9a98eb6)
![Screenshot 2024-10-10 222101](https://github.com/user-attachments/assets/39e2786a-2960-42e1-abed-8cdbcb8e983e)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-10 191313](https://github.com/user-attachments/assets/98c13ac5-174c-4c3d-9af3-3729e11ec6db)


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-10 191324](https://github.com/user-attachments/assets/e6602931-f98d-4087-b225-634c1753ff0a)
![Screenshot 2024-10-10 191339](https://github.com/user-attachments/assets/f5065f8e-ea93-415a-a5a1-87cf6f5bc0ec)
![Screenshot 2024-10-10 191349](https://github.com/user-attachments/assets/a5b7abe7-5891-4b4c-9f2e-46131c674321)


### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-10 191444](https://github.com/user-attachments/assets/6abb9aa9-4d16-4f57-ab7f-cda88f4f415b)


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

