# 🔒 Security Group Setup (Salary API)


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 8-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |


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
| Salary-Non-Prod-Dev-SG	      | 22    | 20.0.0.0/28           |
| Salary-Non-Prod-Dev-SG        | 8080  | Frontend-lb-sg        |

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

![image](https://github.com/user-attachments/assets/1a83c27e-96d5-4278-8278-7af466625b73)





### Step 4: Create or Select a Security Group

1. **Create a New Security Group** by clicking **Create Security Group**, or select an existing one.
2. Provide a **name**, **description**, and **VPC assignment** for your new security group.
![image](https://github.com/user-attachments/assets/6e8162ff-bbb7-4e8c-8906-b00911f81b17)





### Step 5: Define Inbound Rules

1. Click the **Inbound Rules** tab.
![image](https://github.com/user-attachments/assets/e532ebea-2104-4725-9d3d-29fab341644b)




2. Click **Edit Inbound Rules** and add rules based on your requirements:
   ![image](https://github.com/user-attachments/assets/3fa33b72-d76c-4428-95ed-99531c165d7f)






| Security Group Name | Port  | Source          |
|---------------------|-------|-----------------|
| Salary-Non-Prod-Dev-SG       | 22    | 20.0.0.0/28     |
| Salary-Non-Prod-Dev-SG      | 8080  | Frontend-lb-sg  |


### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.
![image](https://github.com/user-attachments/assets/5de54eb9-b416-4e27-9892-015f3bd61358)




2. Click **Edit Outbound Rules** and set outbound traffic settings:
![image](https://github.com/user-attachments/assets/a597065e-de4e-42a9-8b9c-b4676cb1aebe)






| Security Group Name | Port        | Protocol  | Destination  |
|---------------------|-------------|-----------|--------------|
| *                   | All Traffic | All       | 0.0.0.0/0    |



---

## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |

---

## 📚 References

| Description               | Link                                                                 |
|---------------------------|----------------------------------------------------------------------|
| Documentation Template     | [Application Template] |
| Dev Infra Design           | [Cloud Infra Design]
| Security Group Setup Guide | [AWS Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |


