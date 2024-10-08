# Code Coverage- Declarative Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">


---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 04-10-2024  | Version 1.2  | Megha Tyagi     | 07-10-2024     |

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
This document provides an overview of implementing code coverage in a Python project using a Jenkins declarative pipeline. By integrating code coverage tools such as pytest-cov, we can ensure that their test suite effectively covers critical parts of the codebase, leading to better software quality and reliability. The steps outlined in this pipeline automate the testing and code coverage reporting process.

---

## ⚙️ Pre-requisites

| Requirement         | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Python Version**   | Python 3.10 or later.                                                       |
| **Jenkins**          | Jenkins installed and configured.                                           |
| **Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **Python3-venv**     | Install the `python3-venv` package on the Jenkins server for virtualenv setup.|
| **pip**              | Python package installer (pip) must be available to install dependencies.   |
| **pytest**           | pytest and pytest-cov packages must be installed for testing and coverage.  |
| **Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access.|

---

## 💥 Steps to Configuration Code Coverage
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Code Coverage`).
<img width="942" alt="item" src="https://github.com/user-attachments/assets/f6ace938-8206-4294-a6ee-88742d4d7851">


### 3. 🚀 Provide a description for the pipeline that performs Code Coverage in Python code.
<img width="946" alt="description" src="https://github.com/user-attachments/assets/337ceba5-2491-4f45-9283-07a841e989b0">

### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM.
![Screenshot 2024-10-07 131850](https://github.com/user-attachments/assets/dc9db802-faad-4cb9-bd26-8a30a7ef5d1e)
![Screenshot 2024-10-07 131906](https://github.com/user-attachments/assets/b9525bd1-4592-4472-8e1b-1a672f862d4f)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Code Coverage in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 131923](https://github.com/user-attachments/assets/bec0556f-651e-4bdc-bf6b-85ebeabad995)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-07 131943](https://github.com/user-attachments/assets/c200152d-86d3-4680-b4c3-c82a4f20a27b)


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 132034](https://github.com/user-attachments/assets/7b7001ac-4983-4172-ab92-639bce1226a8)
![Screenshot 2024-10-07 132045](https://github.com/user-attachments/assets/43bf8466-f527-4bf4-949b-e03402cac058)
![Screenshot 2024-10-07 132056](https://github.com/user-attachments/assets/8d4bfd79-156b-44bc-923e-b3ba93b273b1)


### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 132119](https://github.com/user-attachments/assets/3094fecc-a340-4470-ba48-d207372026b9)


---

## 📛 Conclusion
In summary, implementing code coverage in your project is essential for ensuring code quality and reliability. By utilizing tools like `pytest` and `pytest-cov`, you can systematically evaluate how well your tests cover your codebase. Regularly monitoring code coverage will enhance your development workflow, foster collaboration among team members, and contribute to the overall success of your software projects.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@ganesharavind124/building-a-jenkins-pipeline-for-code-quality-and-continuous-integration-4c57f0365838| **Medium** |
|https://reddeppa-s.medium.com/jenkins-pipeline-as-code-21b71d8f823a| **Medium** |





