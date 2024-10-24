
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
5.The AMI will appear under the AMIs section after creation.
![Screenshot from 2024-10-21 04-12-39](https://github.com/user-attachments/assets/89766762-ad81-4bfb-b1dd-bf17816818a5)

### Step 2: Create a Launch Template.
1. In the EC2 console, go to Launch Templates and click Create launch template.
- Give the template a name and description(Optional).
![Screenshot from 2024-10-21 04-15-42](https://github.com/user-attachments/assets/75f9f3b7-91a1-4202-b5f3-0b3846b42d60)

2. Select the previously created AMI for Frontend.
![Screenshot from 2024-10-21 04-18-00](https://github.com/user-attachments/assets/ce7bbff2-7986-4ff6-b798-5823f42a849c)

3. Choose the instance type and key pair.
![Screenshot from 2024-10-21 04-21-54](https://github.com/user-attachments/assets/4adf5fb7-279b-40b1-abcf-4cc568e8ae14)

4. Configure network settings as needed & Click Create launch template.
![Screenshot from 2024-10-21 04-24-46](https://github.com/user-attachments/assets/37dfa8a5-3709-4f30-ba3a-9b6125b0a0ce)

### Step 3: Create an Auto Scaling Group
1. Open Auto Scaling Groups in the EC2 console.
2. Click Create Auto Scaling group and give preffered name.
![Screenshot from 2024-10-21 05-02-53](https://github.com/user-attachments/assets/60612ac9-4d81-48c0-aee5-5f11a276c5ad)
3. Select your launch template & Click next.
![Screenshot from 2024-10-21 05-03-41](https://github.com/user-attachments/assets/4c075dec-5ff0-4ad0-b971-5a11087f79d9)
4. Choose Your VPC & Subnet
![Screenshot from 2024-10-21 05-05-11](https://github.com/user-attachments/assets/c57d4e2f-aaf5-4021-b0a1-7d425e571cde)
5. Optionally, link your Auto Scaling group to a Load Balancer.





