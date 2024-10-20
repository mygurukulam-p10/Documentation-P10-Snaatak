
<img width="470" alt="1684234129196" src="https://github.com/user-attachments/assets/da7044c3-99d8-4790-8577-10d4e7fc5683">



# Setup Auto Scaling for Frontend API

| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Aayush Gaur | 18-10-2024   | 1.0     | Aayush Gaur     | 18-10-2024      |

---
---

## 📑 Table of Contents

1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Steps to Setup Auto Scaling](#Steps-to-Setup-Auto-Scaling)
4. [Output](#Output)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)

---

## 🌟 Introduction

Amazon EC2 Auto Scaling helps you make sure you have the right number of servers (EC2 instances) running to handle your application's needs. You set rules for the minimum, maximum, and ideal number of instances you want in an Auto Scaling group. Based on how busy your application gets, Auto Scaling will automatically add more instances when needed or remove them when demand goes down. This way, you only pay for the resources you actually need while keeping your application running smoothly without overloading or wasting resources.

---

## 🔑 Pre-requisites

- Access to the AWS Management Console or AWS CLI with appropriate permissions.
- Knowledge of your application's [network requirements]
---

## 🛠️ Steps to Setup Auto Scaling
### Step 1: Create an AMI Image of the Frontend API Instance
1.  Go to the Amazon EC2 console.
2. Select the Dev-OTMS-Frontend instance, Choose ```Actions```, Then ```Image and templates```, & ```Create Image```
3. Name your AMI and add a description(Optional).
![Screenshot from 2024-10-21 04-07-33](https://github.com/user-attachments/assets/891e792d-1263-4ea7-b49f-ff5b3f88293b)
4. Click Create image.
![Screenshot from 2024-10-21 04-09-28](https://github.com/user-attachments/assets/06710e6e-11b0-48d7-8397-af0df02d351b)

