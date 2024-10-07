# **Setup Listener Rules for Load Balancer (Salary API)**

| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 05-10-2024         | 0.1        | Brij Singh   | Listener Rules for Load Balancer             |
---

## **Table of Contents**  
1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Steps to Setup Listener Rules for Load Balancer](#Steps-to-setup-Listener-Rules-for-Load-Balancer)
4. [Output](#Output)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)

---

## **Introduction** ![intro](https://img.icons8.com/fluency/48/000000/server.png)
**Load balancing** in AWS ensures high availability and reliability by distributing network traffic across multiple resources. This helps optimize resource utilization and maintain performance. This document provides steps to configure load balancer listener rules for your Salary API.

---

## **Pre-requisites** ![prerequisite](https://img.icons8.com/fluency/48/000000/checklist.png)
- AWS Management Console or AWS CLI access with proper permissions.
- Understanding of your application's [network requirements](https://github.com/CodeOps-Hub/Documentation/blob/main/Application_CI/Design/09-%20Cloud%20Infra%20Design/Cloud-Infra-Design-Dev.md).

---

## **Steps to Setup Listener Rules for Load Balancer** ![steps](https://img.icons8.com/fluency/48/000000/connection.png)

### **Step 1: Create Target Group**
1. Open the Amazon EC2 console at _https://console.aws.amazon.com/ec2/_.
2. Navigate to `Target Groups` and select `Create target group`.
   ![Target Group](https://img.icons8.com/fluency/48/000000/add-database.png)
3. Select `Instances` or `IP` for your target type.  
   ![Target Instances](https://img.icons8.com/color/48/000000/ip-address.png)
4. Enter a target group name (e.g., `Dev-salary-tg`) and select a VPC.
5. Configure the health check endpoint and register targets. Set the port to `8080`.
6. Once targets are registered, proceed with default configurations.

### **Step 2: Add Listener Rules to the Load Balancer**
1. In the EC2 console, choose `Load Balancers` and select `Dev-ALB`.
2. Click on `Protocol Port HTTP:80` and add a rule.
   ![Add Rule](https://img.icons8.com/fluency/48/000000/add-rule.png)
3. Define **Name** and relevant tags.
4. Set the **path condition** (e.g., `/item/*`) and forward traffic to the target group.
   ![Path Condition](https://img.icons8.com/external-smashingstocks-circular-smashing-stocks/48/000000/external-path-graphic-design-smashingstocks-circular-smashing-stocks.png)
5. Assign a rule priority, review, and create the rule.

---

## **Output** ![output](https://img.icons8.com/fluency/48/000000/output.png)
- After following the steps, you will successfully configure listener rules for your Salary API load balancer.
- Test by sending a request to the DNS and ensure the API is running properly.

---

## **Conclusion** ![conclusion](https://img.icons8.com/fluency/48/000000/conclusion.png)
This guide provides a straightforward process to set up listener rules, helping users effectively manage traffic, enhance performance, and optimize AWS infrastructure resources.

---

## **Contact Information** ![contact](https://img.icons8.com/fluency/48/000000/contacts.png)

| Name          | Email                                      |
| ------------- | ------------------------------------------ |
| Harshit Singh | harshit.singh.snaatak@mygurukulam.co        |

---

## **References** ![references](https://img.icons8.com/fluency/48/000000/documentation.png)

| Description               | Link                                                                 |
| --------------------------| -------------------------------------------------------------------- |
| Documentation Template     | https://github.com/OT-MICROSERVICES/documentation-template/wiki     |
| Dev Infra Design           | https://github.com/CodeOps-Hub/Documentation/blob/main/...          |
| Listener Rules             | https://docs.aws.amazon.com/elasticloadbalancing/latest/application |

