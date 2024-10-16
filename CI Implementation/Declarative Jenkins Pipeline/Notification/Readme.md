# Notification- Declarative Jenkins Pipeline  <img width="53" alt="icon" src="https://github.com/user-attachments/assets/e86aebb0-b6ef-4e9b-91f8-2ae7aca3651d">

---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 03-10-2024  | Version 1.2  | Megha Tyagi     | 07-10-2024     |       Ayush Yadav           |  Rishabh               |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Declarative pipelines for Notifications](#-steps-to-conguration-declarative-pipelines-for-notification)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document provides a guide on setting up automated email notifications in Jenkins for a CI/CD pipeline. It explains how to configure the pipeline to notify recipients of build success or failure, ensuring timely updates on project status. The guide includes details on code checkout, report archiving, and email notification steps. Customization options for the recipient and notification content are also covered. This setup simplifies monitoring by automating build status alerts.

---

## ⚙️ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Email Notification Plugin**: For performing the actual notification.
3. **Jenkins Credentials**: Add any required credentials (e.g., GitHub tokens) in Jenkins.
---

## 💥 Steps to Configuration Declarative pipelines for Notifications.

### 1. 🚀 Open your Jenkins Dashboard.
<img width="951" alt="Screenshot 2024-10-03 171617" src="https://github.com/user-attachments/assets/e6448943-be68-4a6f-91d1-76e29d206a2f">

### 2. 🚀 Go to the **Manage Jenkins**.** ---> **click on the credentials.
<img width="941" alt="manage jenkins" src="https://github.com/user-attachments/assets/598345b0-9f54-4989-9df1-ce7be107b852">

![credentials](https://github.com/user-attachments/assets/88417a5b-e380-4d81-a85b-10fc438c7cf4)


### 3. 🚀 Go to the global and add email credential.
<img width="959" alt="add cred" src="https://github.com/user-attachments/assets/a41e8ffa-b6b1-470f-bbd4-17c9901708c5">


### 4. 🚀 Now, when you write the pipeline, add one step for email notification in your declarative pipeline-
<img width="947" alt="email script" src="https://github.com/user-attachments/assets/c1a0acdd-1244-40de-a964-30ecf2ab9096">


### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Once the build is successfull, here we can see the build report status-
<img width="947" alt="build report status" src="https://github.com/user-attachments/assets/2b6b6161-e22d-42cf-8d51-94488b0d0f6f">


### 7.🚀 Beside we get the notification on email with the Report(JSON, HTML etc.).
<img width="740" alt="email ss" src="https://github.com/user-attachments/assets/3220cc10-3d7c-4b1b-b671-a9a80e924b81">

![html](https://github.com/user-attachments/assets/da85494b-af00-45f7-aa44-ab2e69f359ec)

---

## 📛 Conclusion
This document has outlined the steps to set up automated email notifications in Jenkins, enabling seamless communication of build status to recipients. By implementing this pipeline, you can ensure timely updates on project progress, whether the build succeeds or fails. 

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
|https://pradeep-sg406.medium.com/how-to-configure-email-notification-in-jenkins-227b58d3c017| **Medium** |
|https://datavalley.ai/configure-email-notification-in-jenkins/?srsltid=AfmBOorJMlxZmvIwsAMNaz8ftmMwI8p24s0PPywNVp6pLRrlwZjfysJZ| **Datavalley** |

