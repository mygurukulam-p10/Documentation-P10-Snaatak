# Setup Security Group for Frontend

| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Aayush Gaur  | -10-2024   | 1.0     | Aayush Gaur      | 18-10-2024      |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [How AWS Security Groups Work](#How-Do-AWS-Security-Groups-Work)
+ [Why Use Security Group](#Why-Use-Security-Group)
+ [Pre-requisites](#Pre-requisites)
+ [Steps to Create a Security Group](#Steps-to-Create-a-Security-Group)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

AWS Security Groups are like a protective shield for your AWS resources, such as EC2 instances. They act as a virtual firewall that controls what traffic can come in (inbound) and go out (outbound) from your AWS resources.

Each security group has a set of rules that decide which traffic is allowed to access your resources. You can set up these rules to control both incoming and outgoing traffic. This helps you manage and protect access to your resources, keeping your data and applications secure.

***

## How Security Groups Work

Here's a simplified breakdown of the process:

- **Inbound Traffic:** These rules decide what kind of traffic is allowed into your resource. For example, you can allow traffic from the internet (like web browsers) on specific ports, such as port 80 for web traffic (HTTP) or port 22 for SSH.

- **Outbound Traffic :** These rules decide what traffic is allowed to go out from your resource to other networks or the internet. You might allow your server to send data to a database or let users connect to a remote service.

- **Stateful:** Security Groups are stateful, meaning if you allow traffic to come into your resource, the response traffic is automatically allowed back out, even if there’s no specific rule for it.

***
## Why Use Security Group

| **Reason**                     | **Explanation**                                                                                 |
|---------------------------------|-----------------------------------------------------------------------------------------------|
| **Control Access to Resources**  | Security groups let you define which traffic can reach your resources, ensuring only authorized access. |
| **Simplify Security Management** | You can apply security groups to multiple instances, making it easy to manage security rules across resources. |
| **Automatically Block Unwanted Traffic** | By default, all traffic is blocked unless allowed by the rules, so you don’t need to worry about accidental access. |
| **No Need for Manual Responses** | Security groups are stateful, meaning they automatically allow response traffic, simplifying the setup. |


***

## Pre-requisites
Access to the AWS Management Console or AWS CLI.
Basic understanding of your application's

***
## Steps to Create a Security Group 

### Step 1: Access AWS Management Console
- **Sign in** to the AWS Management Console with your credentials.

### Step 2: Open EC2 Dashboard
- In the AWS Console, go to **Services** → **EC2**

### Step 3: Navigate to Security Groups
- In the **EC2 Dashboard**, select **Security Groups** from the left-hand menu under Network & Security.

### Step 4: Create or Select a Security Group
- **Security Group Name:**  Give name to your security group according to your preference

- **Description:** Provide a brief description of the security group's purpose.

- Choose your vpc where the security group will be created.
![Screenshot from 2024-10-18 16-24-11](https://github.com/user-attachments/assets/feca385a-1c61-4177-87af-c436072ca325)

### Step 5: Define Inbound Rules
- Click the Add Rule button and add the rule.




