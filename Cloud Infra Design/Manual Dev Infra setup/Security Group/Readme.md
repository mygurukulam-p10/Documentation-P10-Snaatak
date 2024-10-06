# 🔒 Security Group Setup (Salary API)



| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 05-10-2024         | 0.1        | Brij Singh   | Security Group Setup              |


---

## 📑 Table of Contents

1. [Introduction](#introduction)
2. [Pre-requisites](#pre-requisites)
3. [Important Ports](#important-ports)
4. [Setup Steps](#setup-steps)
5. [Contact Information](#contact-information)
6. [References](#references)

---

## 📝 Introduction

This guide walks you through setting up **Security Groups** for the Salary API. Security groups control network traffic to and from your Salary API instances, enhancing security by managing access.

A **security group** acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic. Once linked to an instance, it regulates the traffic entering or leaving that instance.



---

## ✅ Pre-requisites

- Access to the AWS Management Console or AWS CLI.
- Basic understanding of your application's 
---

## 🔑 Important Ports

### Inbound Rules

| Security Group Name | Port  | Source                |
|---------------------|-------|-----------------------|
| Salary-SG-Dev-OT-Microservice	      | 22    | 20.0.0.0/28           |
| Salary-SG-Dev-OT-Microservice	        | 8080  | Frontend-lb-sg        |

### Outbound Rules

| Security Group Name | Port         | Protocol  | Destination  |
|---------------------|--------------|-----------|--------------|
| *                   | All Traffic  | All       | 0.0.0.0/0    |

---

## 🛠️ Setup Steps

### Step 1: Access AWS Management Console

1. **Sign in** to the AWS Management Console with your credentials.

### Step 2: Open EC2 Dashboard

1. In the AWS Console, go to **Services** → **EC2** under the "Compute" section.

### Step 3: Navigate to Security Groups

1. In the **EC2 Dashboard**, select **Security Groups** from the left-hand navigation menu.



### Step 4: Create or Select a Security Group

1. **Create a New Security Group** by clicking **Create Security Group**, or select an existing one.
2. Provide a **name**, **description**, and **VPC assignment** for your new security group.
![image](https://github.com/user-attachments/assets/a0bf14d5-bfa7-4f63-ba37-9868d7f81ca2)




### Step 5: Define Inbound Rules

1. Click the **Inbound Rules** tab.
![image](https://github.com/user-attachments/assets/8363080a-2de2-4fda-8178-3ef28df9071c)



2. Click **Edit Inbound Rules** and add rules based on your requirements:
   ![image](https://github.com/user-attachments/assets/b0126fd3-ca95-4b5f-b7f0-9168ded3cf4a)





| Security Group Name | Port  | Source          |
|---------------------|-------|-----------------|
| Salary-SG-Dev-OT-Microservice        | 22    | 20.0.0.0/28     |
| Salary-SG-Dev-OT-Microservice      | 8080  | Frontend-lb-sg  |


### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.
  ![image](https://github.com/user-attachments/assets/806c1618-44a1-4cbc-812e-48fea5a4a93c)



2. Click **Edit Outbound Rules** and set outbound traffic settings:
![image](https://github.com/user-attachments/assets/5ee38148-6c01-40ab-8c88-f045d4dfed77)





| Security Group Name | Port        | Protocol  | Destination  |
|---------------------|-------------|-----------|--------------|
| *                   | All Traffic | All       | 0.0.0.0/0    |



---
## 📧 Contact Information

For any queries or further information, feel free to contact:

| 👨‍💻 Name | 📧 Email Address |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |

---

## 📚 References

| Description               | Link                                                                 |
|---------------------------|----------------------------------------------------------------------|
| Documentation Template     | [Application Template] |
| Dev Infra Design           | [Cloud Infra Design]
| Security Group Setup Guide | [AWS Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |

