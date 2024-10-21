# Notification for Python- Shared Library 
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 15-10-2024  | Version 1  | Megha Tyagi     | 21-10-2024     |      Ayush            |     Deepak            |   Anjali Kaushal|

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

![Screenshot 2024-10-21 102355](https://github.com/user-attachments/assets/d44e9ad6-7f7f-4e56-834f-1f0e76295827)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Notification in the pipeline script.
![Screenshot 2024-10-21 102346](https://github.com/user-attachments/assets/2d6d6dcc-ac97-48d4-a73a-62f318682545)



### 6. 🚀 Then Click on build to run the pipeline to perform.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">



### 7.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-21 102306](https://github.com/user-attachments/assets/3e97cb35-92d1-412a-8db7-ca3dbfae405d)

![Screenshot 2024-10-21 102323](https://github.com/user-attachments/assets/dcc3b776-e14e-410b-9e10-301f48d926ae)
![Screenshot 2024-10-21 102250](https://github.com/user-attachments/assets/05bfd0ae-e61c-4f96-b7a9-88aba910f7b1)



### 8. Here is the email notification for the status of build.
<img width="786" alt="image" src="https://github.com/user-attachments/assets/a261012a-5b9a-41a2-ba5a-6b201ee72179">


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


