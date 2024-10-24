# 🔒 Security Group Setup (Employee API)


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 09-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |


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

This guide walks you through setting up **Security Groups** for the Employee API. Security groups control network traffic to and from your Employee API instances, enhancing security by managing access.

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
| 	OTMS-Dev-SG-Frontend-api      | 22    |       Open-VPN-Dev-SG|
| OTMS-Dev-SG-Employee-api        | 8080  | OTMS-Dev-SG-Employee-ALB        |


### Outbound Rules

| Security Group Name | Port         | Protocol  | Destination  |
|---------------------|--------------|-----------|--------------|
|  OTMS-Dev-SG-Employee-api                     | All Traffic  | All       | 0.0.0.0/0    |

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
![Screenshot from 2024-10-09 16-26-12](https://github.com/user-attachments/assets/c37f13b3-853e-4758-8fa7-f9a13efe7e44)







### Step 5: Define Inbound Rules

1. Click the **Inbound Rules** tab.
![Screenshot from 2024-10-09 16-09-10](https://github.com/user-attachments/assets/88c3fd17-1b0a-4918-9162-03d3660abee4)


### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.


2. Click **Edit Outbound Rules** and set outbound traffic settings:
![image](https://github.com/user-attachments/assets/5de54eb9-b416-4e27-9892-015f3bd61358)

---

## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |

---

## 📚 References

| Description               | Link                                                                 |
|---------------------------|----------------------------------------------------------------------|
| Security Group Setup Guide 1 | [AWS Security Groups Overview](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)  |
| Security Group Setup Guide 2 | [Managing Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html)    |
| Security Group Setup Guide 3 | [Security Groups Rules](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroupRules.html)    |






