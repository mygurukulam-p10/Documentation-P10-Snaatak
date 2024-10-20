# Notification for Python- Shared Library 
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 15-10-2024  | Version 1  | Megha Tyagi     | 18-10-2024     |                  |                 |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🚀 Global Configurations](-global-configuration)
4. [💥 Steps to Configuration Notification](#-steps-to-conguration-notification)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This readme me explain to introduce email notifications through a Jenkins Shared Library,you define a reusable function in the library that handles sending emails. 
This function can be called in any pipeline to notify users of build status (pass or fail). 

---

## ⚙️ Pre-requisites

| Requirement            | Description                                         |
|------------------------|-----------------------------------------------------|
| Python                 | Ensure Python is installed on your system.         |
| Pip                    | Python package installer, should be installed.     |
| Virtual Environment     | Use a virtual environment to avoid dependency conflicts. |
| Flake8                 | Install Flake8 for linting and Notification.       |
|Notification            |Email-Should be configured in jenkins|

---
## 🚀 Global Configuration
**Here we do global configuration for shared library, go to manage jenkins.....> system......> Global Trusted Pipeline Libraries & provide the required details as you can see in images-**
![Screenshot 2024-10-14 150428](https://github.com/user-attachments/assets/f88f3a86-1823-4f72-ad64-0adfd641a988)
![Screenshot 2024-10-14 150516](https://github.com/user-attachments/assets/8fbb331d-41fd-4a9f-8eea-8838d370eab1)

---


## 💥 Steps to Configuration to Notification
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Notification`).
![Screenshot 2024-10-18 000454](https://github.com/user-attachments/assets/bdfd0ca0-6db2-445c-98ea-70bdd97b4468)



### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Screenshot 2024-10-18 105533](https://github.com/user-attachments/assets/2a854329-3399-470d-a971-3ebd7911ff6e)




### 4. 🚀 Create the repo & vars file which will be using in pipeline script.
![Screenshot 2024-10-18 105812](https://github.com/user-attachments/assets/274d0dd5-cd6e-40f1-831c-955453fe03ed)
![Screenshot 2024-10-18 105820](https://github.com/user-attachments/assets/13da0081-d167-490a-87ce-2088257504cb)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Notification in the pipeline script.
![Screenshot 2024-10-18 105758](https://github.com/user-attachments/assets/d8a7b62b-63ec-4683-a6b9-aeb11f10ea41)



### 6. 🚀 Then Click on build to run the pipeline to perform.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">



### 7.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-18 104425](https://github.com/user-attachments/assets/6170a5c1-b552-447f-8c43-0aa38fb7ba3e)
![Screenshot 2024-10-18 104437](https://github.com/user-attachments/assets/6f6ea12e-078b-4d21-98a8-e3b8496ab1f3)
![Screenshot 2024-10-18 104455](https://github.com/user-attachments/assets/e5fffdae-998c-4998-b68e-99159cb1a63f)
<img width="959" alt="image" src="https://github.com/user-attachments/assets/521705aa-0bea-499a-b8f2-166006bd7cad">



### 9. Here is the email notification for the status of build.
![Screenshot 2024-10-18 104403](https://github.com/user-attachments/assets/84067b9a-725c-4e23-b0a8-838ca0a20437)


---

## 📛 Conclusion
Using a Jenkins Shared Library for email notifications streamlines the process of sending consistent build status alerts across multiple pipelines.
It promotes code reusability and simplifies pipeline maintenance. This approach enhances scalability and efficiency in managing Jenkins pipelines.

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
|https://plugins.jenkins.io/email-ext/| **Jenkins Doc** |
|https://pradeep-sg406.medium.com/how-to-configure-email-notification-in-jenkins-227b58d3c017| **Medium** |


