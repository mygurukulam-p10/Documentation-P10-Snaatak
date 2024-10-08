# 🔒 Security Group Setup for Postgresql Manually 

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 08-10-2024  | Version 1  | Vinay Bansal    | 08-10-2024     |

---

## 📑 Table of Contents

1. [📝 Introduction](#-introduction)
2. [✅ Pre-requisites](#-pre-requisites)
3. [🔑 Important Ports](#-important-ports)
4. [🛠️ Setup Steps](#-setup-steps)
5. [💡 Best Practices for Security](#-best-practices-for-security)
6. [✅ Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

---

## 📝 Introduction

This guide walks you through setting up **Security Groups** for the Postgresql. Security groups control network traffic to and from your Postgresql instances, enhancing security by managing access.

A **security group** acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic. Once linked to an instance, it regulates the traffic entering or leaving that instance.


## ✅ Pre-requisites

- Access to the AWS Management Console or AWS CLI.
- Basic understanding of your Database.
-  
## 🔍 Security Group Overview

Security groups act as virtual firewalls that control inbound and outbound traffic for Postgresql. They define rules that specify the allowed ports, protocols, and IP ranges for communication between nodes, clients, and external systems.


## ⬇️ Inbound Rules

Inbound rules determine what traffic is allowed to reach the Postgresql instances. The following rules should be considered:

| Port  | Protocol | Description                             |
|-------|----------|-----------------------------------------|
| 22	      | SSH    |     To securely connect to a remote device      |
| 5432  | TCP      | used by the PostgreSQL Database Server |



## ⬆️ Outbound Rules

Outbound rules define the traffic allowed to leave the ScyllaDB instances. 
| Destination IP/CIDR  | Port  | Protocol | Description                              |
|-----------------------|-------|----------|------------------------------------------|
| `0.0.0.0/0`           | All   | All      | Allow all outbound traffic (customize as needed). |


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
![4](https://github.com/user-attachments/assets/a64b14e1-1c22-4bfd-a65d-e6981665c2d0)

### Tag
![5](https://github.com/user-attachments/assets/5fcfcdc5-95bd-4c35-8d03-e8a603e67339)



### Step 5: Define Inbound Rules

1. Click the **Inbound Rules** tab....> Click Edit Inbound Rules and add rules based on your requirements:
2.Add rules based on your requirements.
3. Type: Custom TCP Rule
4. Protocol: TCP
5. Port Range: 5432 (for Postgresql)
6. Source: Specify the security group of the employee app and bastian host security group.
7. Click on Save rules.
![6](https://github.com/user-attachments/assets/58f23946-ca2c-4ee3-a3bc-a9bf570751db)



### Step 6: Define Outbound Rules

1. Click the **Outbound Rules** tab.
![Screenshot 2024-10-08 161247](https://github.com/user-attachments/assets/9fc33a03-e675-4670-b4b1-acb968a26530)


#### 💡 Best Practices for Security
- Limit access to known IP addresses for inbound rules to minimize exposure.
- Regularly review and update security group rules to reflect changes in the network environment.
- Use strong passwords and enable encryption for internal communication between nodes.

  
## ✅ Conclusion

Creating a security group specifically for PostgreSQL enhances the security of your application by controlling access to the database. By following the outlined steps, you can effectively manage inbound and outbound traffic, ensuring that only authorized IP addresses can communicate with your PostgreSQL instance.

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |


---

## 📚 References

| Description               | Link                                                                 |
|---------------------------|----------------------------------------------------------------------|
| Security Group Setup Guide | [AWS Security Groups](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html) |
