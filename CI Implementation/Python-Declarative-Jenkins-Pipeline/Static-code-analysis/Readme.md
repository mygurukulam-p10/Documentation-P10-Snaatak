# Static Code Anaylsis- Declarative Jenkins Pipeline <img width="33" alt="logo" src="https://github.com/user-attachments/assets/52548837-3a11-4ee6-858f-d04223c52fcc">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 04-10-2024  | Version 1  | Megha Tyagi     | 04-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Static Code Analysis](#-steps-to-conguration-static-code-analysis)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
Static code analysis is essential for maintaining code quality and identifying potential issues before deployment. This document outlines the steps to set up a Jenkins declarative pipeline for static code analysis using Python and Pylint. Integrating this process into CI/CD helps ensure cleaner, more reliable code.

---

## ⚙️ Pre-requisites

| Requirement                        | Description                                                      |
|------------------------------------|------------------------------------------------------------------|
| Jenkins Installed                   | Ensure Jenkins is installed and properly configured on your server. |
| Git Plugin for Jenkins              | The Git plugin must be installed in Jenkins to allow for repository checkouts. |
| Python and Pylint Installed         | Python and Pylint should be installed in the environment where Jenkins runs. |

---

## 💥 Steps to Configuration Static Code Analysis

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Static Code Analysis`).
<img width="946" alt="new item" src="https://github.com/user-attachments/assets/e8ce676b-3217-4ec7-a0ba-c92b19ba9fcd">

### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="944" alt="description" src="https://github.com/user-attachments/assets/b1066678-79ab-4517-b716-12a4986b4ba0">

### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM.
![Screenshot 2024-10-07 133123](https://github.com/user-attachments/assets/8bb95046-8c1d-467a-b776-d35d457631e0)
![Screenshot 2024-10-07 133131](https://github.com/user-attachments/assets/af42d98a-b1dd-4a2d-971b-d6c37816aa6c)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Static Code analysis in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 133207](https://github.com/user-attachments/assets/cc1ca081-7b7d-4ba9-a2bb-885659b2472e)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-07 133245](https://github.com/user-attachments/assets/4f32f8bb-c26e-4927-bbcf-3ad5629e9460)


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 134245](https://github.com/user-attachments/assets/2728bf40-49a6-46fa-a64a-be5d845cbd3b)
![Screenshot 2024-10-07 134257](https://github.com/user-attachments/assets/fd2a6c7f-50ad-4be7-81e8-8d03d1b1080b)

### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 134324](https://github.com/user-attachments/assets/b7a0b419-94b2-4610-86d4-6fc15ced8475)

---

## 📛 Conclusion
Integrating static code analysis into a Jenkins declarative pipeline enhances code quality by identifying issues early in development. By following the outlined steps, teams can automate the analysis process with Python and Pylint. This practice fosters a culture of quality, resulting in more maintainable.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@tlilyskander/static-code-analysis-with-pylint-49a078f029cf| **Medium** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Static%20code%20analysis| **Documentation** |
|https://tinyurl.com/ycxxt6py|**Manual POC**|


