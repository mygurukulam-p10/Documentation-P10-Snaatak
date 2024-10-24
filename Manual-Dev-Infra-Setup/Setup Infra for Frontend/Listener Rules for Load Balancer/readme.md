# Setup Listener Rules for Load Balancer for (Frontend API)


|   Author        |  Created on   |  Version   | Last updated by  | Last edited on |
| --------------- | --------------| -----------|----------------- | -------------- |
| Aayush Gaur |  24-10-2024  |  Version 1 | Aayush Gaur  | 24-10-2024    |

***
## Table of Contents
+ [Introduction](#Introduction)
+ [Why use AWS Load Balancer](#Why-use-AWS-Load-Balancer)
+ [Listener Rules](#Listener-Rules)
+ [Pre-requisites](#Pre-requisites)
+ [Steps to setup Listener Rules for Load Balancer](#Steps-to-setup-Listener-Rules-for-Load-Balancer)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)
  
***
## Introduction

In AWS, load balancing refers to the process of distributing incoming network traffic across multiple servers or resources to enhance the availability, scalability, and reliability of applications. By dynamically distributing requests, load balancers ensure that no single server is overwhelmed, leading to optimized resource utilization, improved performance, and minimized response times. This approach helps maintain application stability even during traffic spikes, preventing downtime and ensuring seamless user experiences. AWS offers services like Elastic Load Balancing (ELB) to automatically balance traffic and ensure smooth operations across different instances and regions.

***
## Why use AWS Load Balancer

| Benefit               | Description                                                                                                                                                                        |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Fault Tolerance**    | Load balancers continuously monitor the health of instances, ensuring that traffic is routed only to healthy ones. This enhances fault tolerance, preventing service interruptions. |
| **SSL Termination**    | Load balancers offload SSL/TLS encryption and decryption processes, freeing backend servers from these tasks, thereby improving overall system performance and security.            |
| **Improved Performance** | By distributing requests based on factors like server health, network latency, and location, load balancers optimize resource allocation, leading to faster and smoother performance. |
| **Scalability**        | Load balancers support automatic scaling by evenly distributing traffic across multiple servers, allowing resources to grow or shrink as demand fluctuates, ensuring efficient scaling. |
| **High Availability**  | Load balancers distribute incoming traffic across multiple instances, ensuring continuous service availability and preventing downtime by rerouting traffic during server failures.  |

***
## Listener Rules

Listener rules in AWS load balancers define how traffic is routed to target groups based on conditions like HTTP method, path, or source IP. Rules with lower priority are evaluated first. Actions include forwarding to target groups, redirection, or returning fixed responses. If no rules match, a default rule forwards traffic or returns an error response.

***
## Pre-requisites

 * Active Aws Account

***
## Steps to setup Listener Rules for Load Balancer
### Step 1: Create Target Group 🖥️
1. Open the Amazon EC2 console at AWS EC2 Console.
2. In the navigation pane, choose Target Groups and click on Create Target Group.

3. Choose the target type: either Instances or IP.
![Screenshot from 2024-10-24 08-14-40](https://github.com/user-attachments/assets/e2f110de-0658-4743-982c-366ea01b04e9)
4. Enter a target group name (e.g., `OTMS-Dev-TG-Frontend) and choose the appropriate VPC.
![Screenshot from 2024-10-24 08-16-40](https://github.com/user-attachments/assets/26c51a19-c50c-4b70-8a99-2f112b98437b)
