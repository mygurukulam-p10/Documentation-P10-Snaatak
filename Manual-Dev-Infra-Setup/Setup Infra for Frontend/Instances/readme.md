# Setup Instances for Frontend API

 
|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Aayush Gaur |  11-10-2024  | 1.0 | Aayush Gaur  | 11-10-2024    |


## Table of Contents
+ [Introduction](#Introduction)
+ [Why use AWS EC2 Instance](#Why-use-AWS-EC2-Instance)
+ [EC2 instance types](#EC2-instance-types)
+ [Pre-requisites](#Pre-requisites)
+ [Steps to Launch an Ec2 Instance](#Steps-to-Launch-an-Ec2-Instance)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  

## Introduction
An Amazon EC2 instance is like a virtual computer in the cloud that you can create and control through AWS. You can choose how much CPU, memory, storage, and network capacity you want, depending on what your application needs. These instances are started using templates called Amazon Machine Images (AMIs), which come with the operating system and any software you might need.

You can easily manage these instances—start them when needed, stop them when not in use, resize them, or even terminate them to save costs. EC2 instances are a key part of running applications on AWS, giving you the flexibility to scale your resources based on demand while staying cost-effective.

## Why use AWS EC2 Instance
| Feature                 | Description                                                                                                                                                                |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Operating System**     | Supports a wide range of operating systems, such as Linux, Windows Server, CentOS, and Debian, allowing flexibility for various application needs.                          |
| **Persistent Storage**   | Use Amazon EBS (Elastic Block Store) to attach storage to instances, which can be resized as needed and even attached to multiple instances at the same time.               |
| **Elastic IP Addresses** | Easily move static IP addresses between instances without involving network admins, perfect for scenarios like failover clusters or load balancing.                         |
| **Amazon CloudWatch**    | A monitoring tool that helps you track performance data for your applications and AWS resources, making it easier to manage costs and optimize resources based on usage.     |
| **Bare-metal Instances** | Provides direct access to the underlying hardware without virtualization, giving you more control, enhanced security, and higher processing power when needed.               |
| **Pause and Resume**     | Temporarily pause an instance and resume it later from the same state, helping save resources and reduce costs during periods of inactivity.                                  |
## EC2 instance types
| Instance Type            | Description                                                                                                                                                 |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **General Purpose**       | Balanced instances with a mix of compute, memory, and networking. Ideal for everyday tasks like web servers, app servers, and small databases (e.g., t3, m5). |
| **Compute Optimized**     | Designed for tasks needing high CPU performance, such as batch processing, gaming, and machine learning (e.g., c5).                                           |
| **Memory Optimized**      | Provides more memory for applications that need large amounts of data to be processed in memory, like databases and in-memory analytics (e.g., r5, x1).       |
| **Storage Optimized**     | Ideal for applications that require fast, large-scale storage access, like big data processing and data warehousing (e.g., i3, d2).                           |
| **Accelerated Computing** | Uses hardware accelerators (GPUs) to handle tasks like machine learning, graphics processing, and video rendering (e.g., p3, g4).                              |
| **Burstable Instances**   | Offers low-cost instances that can handle spikes in workload with higher performance when needed, ideal for apps with inconsistent traffic (e.g., t3).          |
| **High Performance**      | High-end instances for demanding applications that need direct hardware access and large amounts of computing power (e.g., bare-metal instances).               |

## Pre-requisites
**AWS Acount**

## Steps to Launch an Ec2 Instance
**Step 1: :** Go to the AWS console and sign into your account.
 
**Step 2: :** After logging into the Amazon Management Console, navigate to the EC2 Dashboard.
![Screenshot from 2024-10-11 19-06-45](https://github.com/user-attachments/assets/3f039af3-26d2-4803-b9d0-ace35254443e)

**Step 3:** Choose `Launch Instance` , and give prefered name.
![Screenshot from 2024-10-12 15-02-33](https://github.com/user-attachments/assets/2a1babff-1ba8-4944-8b43-ea604042179f)

**Step 4:** Choose Ubuntu AMI, Select the instance type as t2-micro, Generate a key pair with an appropriate name.
![Screenshot from 2024-10-12 15-08-20](https://github.com/user-attachments/assets/4ffd7abe-7763-4610-9de7-d2178f47c454)

**Step 5:** In The Network Setting choose a VPC; eg, OTMS-Dev. Choose a subnet & Disable auto-assign IP
![Screenshot from 2024-10-12 15-12-59](https://github.com/user-attachments/assets/453e95e1-74a7-40f9-a4b2-8cce9d26a412)

**Step 6:** Choose your security group, eg OTMS-Frontend-Dev, Don't change any setting for now & Launch the Instance.
![Screenshot from 2024-10-12 15-17-51](https://github.com/user-attachments/assets/5f1895c6-0352-4a6e-a337-6df5be70dc1f)

![Screenshot from 2024-10-12 15-18-58](https://github.com/user-attachments/assets/7da69dd6-f2ef-420e-a17b-73ff966a02af)










