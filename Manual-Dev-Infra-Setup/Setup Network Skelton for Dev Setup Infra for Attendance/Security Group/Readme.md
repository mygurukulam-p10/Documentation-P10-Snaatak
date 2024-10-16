# 🔒 Security Group Setup (Attendance API)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |   L0 Reviewer   |  L1 Reviewer| L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 08-10-2024  | Version 1.2  | Megha Tyagi     | 13-10-2024     |  Ayush Yadav                |   Deepak Nishad              |   Anjali Kaushal|

---

## 📑 Table of Contents

1. [📝 Introduction](#-introduction)
2. [✅ Pre-requisites](#-pre-requisites)
3. [🔑 Important Ports](#-important-ports)
4. [🛠️ Setup Steps](#-setup-steps)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---

## 📝 Introduction

This guide walks you through setting up **Security Groups** for the Attendance API. Security groups control network traffic to and from your Attendance API instances, enhancing security by managing access.

A **security group** acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic. Once linked to an instance, it regulates the traffic entering or leaving that instance.



---

## ✅ Pre-requisites

- Access to the AWS Management Console or AWS CLI.
- Basic understanding of your application's 
---

## 🔑 Important Ports

### Inbound Rules

| **Security Group Name**           | **Port** | **Description**                                      | **Destination**                                      |
|-----------------------------------|----------|------------------------------------------------------|------------------------------------------------------|
| Attendance-Non-Prod-Dev-SG        | 22       | Allows secure SSH connections to remote devices       | Remote clients accessing the server via SSH          |
| Attendance-Non-Prod-Dev-SG        | 8080     | Enables access to web services or application endpoints| Web servers and services interacting with the application |
| Attendance-Non-Prod-Dev-SG        | 6379     | Facilitates communication with the Redis database     | Redis clients and applications that interact with Redis |
| Attendance-Non-Prod-Dev-SG        | 5432     | Allows connections to the PostgreSQL database         | PostgreSQL clients connecting to the database         |



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
![Screenshot 2024-10-08 161119](https://github.com/user-attachments/assets/42df9b4b-ed00-4c97-89ee-6c5e43e7f915)


### Step 5: Define Inbound Rules

1. Click the **Inbound Rules** tab....> Click Edit Inbound Rules and add rules based on your requirements:

Below is the list of security groups used for the Attendance-Non-Prod-Dev environment, along with their associated ports and descriptions.
<img width="785" alt="image" src="https://github.com/user-attachments/assets/62b52f1e-d270-4cca-9d41-ed31c16b499e">



### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.
![Screenshot 2024-10-08 161247](https://github.com/user-attachments/assets/9fc33a03-e675-4670-b4b1-acb968a26530)




| Security Group Name | Port        | Protocol  | Destination  |
|---------------------|-------------|-----------|--------------|
| *                   | All Traffic | All       | 0.0.0.0/0    |



---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |


---

## 📚 References

| Description               | Link                                                                 |
|---------------------------|----------------------------------------------------------------------|
| Security Group Setup Guide | [AWS Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |

