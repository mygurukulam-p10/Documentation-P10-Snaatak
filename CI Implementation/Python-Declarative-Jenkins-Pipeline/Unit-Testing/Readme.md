# Unit Testing- Declarative Jenkins Pipeline <img width="29" alt="image" src="https://github.com/user-attachments/assets/032e21f7-1a27-4a35-b7a7-b211671dcf95">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 07-10-2024  | Version 1  | Megha Tyagi     | 07-10-2024     |      Ayush  Yadav          |  Rishabh               |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Unit Testing](#-steps-to-conguration-unit-testing)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document provides a comprehensive guide for setting up unit testing using pytest within a Jenkins declarative pipeline. By integrating pytest into your CI/CD workflow, you can automate the testing process, enabling faster feedback and higher confidence in code changes. Follow the outlined steps to implement effective unit testing in your projects

---

## ⚙️ Pre-requisites

| Prerequisite            | Description                                                    |
|------------------------|---------------------------------------------------------------|
| Python                 | Ensure Python 3.6 or higher is installed on your system.     |
| pip                    | Install `pip`, the package manager for Python.               |
| pytest                 | Install `pytest` using pip: `pip install pytest`.            |
| Requirements File      | Create a `requirements.txt` file if using additional packages.|

---

## 💥 Steps to Configuration to Unit Testing
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Unit Testing`).
<img width="956" alt="image" src="https://github.com/user-attachments/assets/6620207c-7efd-475c-ba45-68dfb2803e1e">

### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Screenshot 2024-10-07 174356](https://github.com/user-attachments/assets/7a1e839d-b70a-485f-a03b-e51bd68d9c9e)


### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script for SCM.
![Screenshot 2024-10-07 183009](https://github.com/user-attachments/assets/dab8e685-54a8-476d-bcdd-4779729e7ae8)
![Screenshot 2024-10-07 183023](https://github.com/user-attachments/assets/f32cc11a-69c2-4cb8-988d-953ef3eebbe6)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Unit Testing analysis in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 181703](https://github.com/user-attachments/assets/729ad404-7933-45c3-81b0-10ba17681784)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-07 181737](https://github.com/user-attachments/assets/e01b2430-0993-4a1f-9f28-f9e4708a9abc)



### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 181852](https://github.com/user-attachments/assets/211e8220-2007-402d-ae8f-746abf963c4a)
![Screenshot 2024-10-07 181912](https://github.com/user-attachments/assets/5b210680-516a-496a-abe4-8c926fe331f3)
![Screenshot 2024-10-07 182007](https://github.com/user-attachments/assets/e5120475-3ad0-4826-88f4-01577b88df64)


### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 181807](https://github.com/user-attachments/assets/85da86db-84d4-4dc4-945b-1c14019442be)

---

## 📛 Conclusion
Implementing unit testing with pytest in a Jenkins pipeline significantly enhances the reliability and maintainability of your code. By automating test execution, you can quickly identify issues and validate functionality after each code change. 

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://priscillastephan.medium.com/unit-testing-guidelines-what-to-test-and-what-not-to-test-9d4c384a142a| **Medium** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Unit%20Testing%20Doc| **Documentation** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Unit%20Testing%20POC|**Manual POC**|



