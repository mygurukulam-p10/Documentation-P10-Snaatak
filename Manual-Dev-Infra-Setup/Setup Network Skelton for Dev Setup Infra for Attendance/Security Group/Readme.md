# 🔒 Security Group Setup (Attendance API)

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 08-10-2024  | Version 1.0  | Megha Tyagi     | 08-10-2024     |

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

| Security Group Name | Port  | Description                |
|---------------------|-------|-----------------------|
| Attendance-Non-Prod-Dev-SG  | 22    | To securely connect to a remote device  |
| Attendance-Non-Prod-Dev-SG  | 8080  | End point|
|Attendance-Non-Prod-Dev-SG   |6379| used by the Redis Database Server|
|Attendance-Non-Prod-Dev-SG   |5432|used by the PostgreSQL Database Server|

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
![Screenshot 2024-10-08 161333](https://github.com/user-attachments/assets/b08a8c2a-1b5b-4191-a3e3-78249eed8a30)


| Security Group Name | Port  | Source          |
|---------------------|-------|-----------------|
| Attendance-Non-Prod-Dev-SG  | 22    | 20.0.0.0/28           |
| Attendance-Non-Prod-Dev-SG  | 8080  | Frontend-lb-sg        |
|Attendance-Non-Prod-Dev-SG   |5432| Redis|
|Attendance-Non-Prod-Dev-SG   |6379|Postgres|


### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.
![Screenshot 2024-10-08 161247](https://github.com/user-attachments/assets/9fc33a03-e675-4670-b4b1-acb968a26530)


2. Click **Edit Outbound Rules** and set outbound traffic settings:
![image](https://github.com/user-attachments/assets/a597065e-de4e-42a9-8b9c-b4676cb1aebe)



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

