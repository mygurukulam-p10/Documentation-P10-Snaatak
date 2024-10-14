# Unit Testing- Shared Library <img width="29" alt="image" src="https://github.com/user-attachments/assets/032e21f7-1a27-4a35-b7a7-b211671dcf95">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 14-10-2024  | Version 1  | Megha Tyagi     | 14-10-2024     |

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
This document provides a comprehensive guide for setting up unit testing using pytest within a Jenkins Shared Library. By integrating pytest into your CI/CD workflow, you can automate the testing process, enabling faster feedback and higher confidence in code changes. Follow the outlined steps to implement effective unit testing in your projects

---

## ⚙️ Pre-requisites

| Prerequisite            | Description                                                    |
|------------------------|---------------------------------------------------------------|
| Python                 | Ensure Python 3.6 or higher is installed on your system.     |
| pip                    | Install `pip`, the package manager for Python.               |
| pytest                 | Install `pytest` using pip: `pip install pytest`.            |


---

## 💥 Steps to Configuration to Unit Testing
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Unit Testing`).
![Screenshot 2024-10-13 193945](https://github.com/user-attachments/assets/7d6e47fe-3840-477a-a9e8-7342f56ff2ed)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Screenshot 2024-10-13 194005](https://github.com/user-attachments/assets/b4e70f2a-ce81-46e1-a4a9-11843a43a9ba)



### 4. 🚀 Create the repo for add jenkinfile which will be using in pipeline script.
![Screenshot 2024-10-14 073934](https://github.com/user-attachments/assets/56850572-a364-4a04-adfc-a27e55c299d0)
![Screenshot 2024-10-14 074113](https://github.com/user-attachments/assets/610f261b-9403-44f5-9abf-5d07a1884299)
![Screenshot 2024-10-14 074129](https://github.com/user-attachments/assets/3b433527-20ed-471f-b115-d6cafa7bc836)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Unit Testing analysis in the pipeline script ...> add repo link & credintial, file path.
![Screenshot 2024-10-14 073855](https://github.com/user-attachments/assets/b69f64ae-db35-4358-b0aa-e800770216fb)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
<img width="959" alt="image" src="https://github.com/user-attachments/assets/9e96fda8-7e40-47bf-90aa-b8ee42e4fbb9">


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-14 073752](https://github.com/user-attachments/assets/acedc3b2-d7a7-46b9-9d2a-c77959c3d9e5)
![Screenshot 2024-10-14 073806](https://github.com/user-attachments/assets/b95c4217-99c7-47a9-926f-2c65257d7e6f)
![Screenshot 2024-10-14 073826](https://github.com/user-attachments/assets/f493b3cc-2187-4fb1-88f0-b3d3aa079cfe)


### 9.🚀 Review the stages of the build process in the console output.
<img width="844" alt="image" src="https://github.com/user-attachments/assets/50a9fbae-97e7-4ff0-8efc-b06bf8bba76f">

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




