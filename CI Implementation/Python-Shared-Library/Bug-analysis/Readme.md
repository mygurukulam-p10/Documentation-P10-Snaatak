# Bug Analysis for Python- Shared Library 
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 14-10-2024  | Version 1  | Megha Tyagi     | 14-10-2024     |                  |                 |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🚀 Global Configurations](-global-configuration)
4. [💥 Steps to Configuration Bug Analysis](#-steps-to-conguration-Bug-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This project aims to implement a robust code analysis tool using Flake8 to ensure high-quality Python code. By identifying stylistic errors and potential bugs, it enhances code maintainability and readability.

---

## ⚙️ Pre-requisites

| Requirement            | Description                                         |
|------------------------|-----------------------------------------------------|
| Python                 | Ensure Python is installed on your system.         |
| Pip                    | Python package installer, should be installed.     |
| Virtual Environment     | Use a virtual environment to avoid dependency conflicts. |
| Flake8                 | Install Flake8 for linting and bug analysis.       |

---
## 🚀 Global Configuration
**Here we do global configuration for shared library, go to manage jenkins.....> system......> Global Trusted Pipeline Libraries & provide the required details as you can see in images-**
![Screenshot 2024-10-14 150428](https://github.com/user-attachments/assets/f88f3a86-1823-4f72-ad64-0adfd641a988)
![Screenshot 2024-10-14 150516](https://github.com/user-attachments/assets/8fbb331d-41fd-4a9f-8eea-8838d370eab1)

---


## 💥 Steps to Configuration to Bug Analysis
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bug Analysis`).
![Screenshot 2024-10-14 224419](https://github.com/user-attachments/assets/62837938-401e-46d1-a1d6-30d6fca2e617)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Screenshot 2024-10-14 224451](https://github.com/user-attachments/assets/339dbc0f-4359-436d-8e2f-5163486afdfa)



### 4. 🚀 Create the repo & vars file which will be using in pipeline script.
![Screenshot 2024-10-14 091456](https://github.com/user-attachments/assets/d7ecabe4-5a4f-4bde-bad2-a0e4db175888)
<img width="959" alt="image" src="https://github.com/user-attachments/assets/6ec39583-ba03-4df4-801d-52dda0245acd">




### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Bug analysis in the pipeline script.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/1d070785-f79b-4199-8aec-c138ee6c2cf6">




### 6. 🚀 Then Click on build to run the pipeline to perform.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete.
![Screenshot 2024-10-14 234052](https://github.com/user-attachments/assets/30ba7c80-5859-44fe-a209-9fd32542b112)



### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-14 234010](https://github.com/user-attachments/assets/2951340f-3fa2-4db2-a985-e27891f55667)

![Screenshot 2024-10-14 234024](https://github.com/user-attachments/assets/1f38e923-c01c-4b04-9f36-46964481b397)
![Screenshot 2024-10-14 234038](https://github.com/user-attachments/assets/1e8d829f-5b68-4dc7-9fd3-9019d6bc4027)


### 9.🚀 Review the stages of the build process in the console output.
<img width="935" alt="image" src="https://github.com/user-attachments/assets/ebe5771a-0a40-44a7-9f64-e995a2c8d9ab">


---

## 📛 Conclusion
Incorporating Flake8 into our development workflow significantly improves code quality and adherence to Python standards. By following this documentation, 
contributors can easily integrate Flake8 into their projects. Together, we can maintain a clean, efficient, and error-free codebase.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co|

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Bugs%20analysis/Bug%20analysis%20Doc| **Doc** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Bugs%20analysis/Bugs%20Analysis%20POC| **POC** |
|https://teachtimes.medium.com/most-common-bugs-in-python-and-how-to-avoid-them-15bae89d1b23|**Medium**|

