# Bugs analysis- Declarative Jenkins Pipeline 


---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 09-10-2024  | Version 1  | Megha Tyagi     | 09-10-2024     |  Ayush Yadav                |     Deepak Nishad            |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Bugs Analysis](#-steps-to-configuration-bugs-analysis)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction

This project aims to implement a robust code analysis tool using Flake8 to ensure high-quality Python code. By identifying stylistic errors 
and potential bugs, it enhances code maintainability and readability.

---

## ⚙️ Pre-requisites

| Requirement            | Description                                         |
|------------------------|-----------------------------------------------------|
| Python                 | Ensure Python is installed on your system.         |
| Pip                    | Python package installer, should be installed.     |
| Virtual Environment     | Use a virtual environment to avoid dependency conflicts. |
| Flake8                 | Install Flake8 for linting and bug analysis.       |

---

## 💥 Steps to Configuration Bugs analysis
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bugs analysis`).
<img width="941" alt="image" src="https://github.com/user-attachments/assets/6ffb3fe4-d718-4edb-bff1-ad86ab42bef0">


### 3. 🚀 Provide a description for the pipeline that performs Bugs analysis in Python code.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/0fb49527-3411-4006-9cad-af12d9aa908e">

### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM.
<img width="949" alt="image" src="https://github.com/user-attachments/assets/85cb5ecc-1425-44c9-b29a-e1b38f333a24">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/87020dab-ef8f-4459-a087-cc56c558c9fc">



### 5. 🚀 Choose Pipeline as the job type-->
- **Add your pipeline script for Bugs analysis in the pipeline script for SCM ...>**
- **add repo link & credintial, file path.**
<img width="944" alt="image" src="https://github.com/user-attachments/assets/a4981e10-afaa-4461-b564-3cea51fc267f">



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
<img width="959" alt="image" src="https://github.com/user-attachments/assets/f2a64751-d1b9-47b8-a6a6-70109675afff">



### 8.🚀 Click on Console Output to see the complete build.
<img width="938" alt="image" src="https://github.com/user-attachments/assets/a0b98bbe-3ce6-4837-8b89-5140dd480b35">
<img width="959" alt="image" src="https://github.com/user-attachments/assets/307ccd28-2c67-4eb9-bb78-133b28360370">
<img width="959" alt="image" src="https://github.com/user-attachments/assets/3fcd4453-2fa9-4c77-ab0e-64dc22e8597e">


### 9.🚀 Review the stages of the build process in the console output.
<img width="958" alt="image" src="https://github.com/user-attachments/assets/96266002-a63a-4b5a-961f-b74a5170e7c6">

---

## 📛 Conclusion
Incorporating Flake8 into our development workflow significantly improves code quality and adherence to Python standards. By following this documentation, 
contributors can easily integrate Flake8 into their projects. Together, we can maintain a clean, efficient, and error-free codebase.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Bugs%20analysis/Bug%20analysis%20Doc| **Doc** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Bugs%20analysis/Bugs%20Analysis%20POC| **POC** |
|https://teachtimes.medium.com/most-common-bugs-in-python-and-how-to-avoid-them-15bae89d1b23|**Medium**|
