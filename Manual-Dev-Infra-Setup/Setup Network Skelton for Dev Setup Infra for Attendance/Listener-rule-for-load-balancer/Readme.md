# **Setup Listener Rules for Load Balancer (Attendance API)**


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 09-10-2024  | Version 1  | Megha Tyagi     | 11-10-2024     |  Ayush Yadav                |     Deepak Nishad            |   Anjali Kaushal|

---
---

## **Table of Contents** 📑
1. [🌐 Introduction](#-introduction)
2. [✔️ Pre-requisites](#-pre-requisites)
3. [⚙️ Steps to Setup Listener Rules for Load Balancer](#-steps-to-setup-listener-rules-for-load-balancer)
4. [📊 Output](#-output)
5. [🎯 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---

## 🌐 Introduction 
**Load balancing** in AWS ensures high availability and reliability by distributing network traffic across multiple resources. This guide will walk you through configuring listener rules for your Attendance API to optimize traffic routing and performance using AWS Load Balancers.

---

## ✔️ Pre-requisites ✔
- **Access** to the AWS Management Console or AWS CLI with appropriate permissions.
- **Understanding** of your application's [network requirements](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Cloud%20Infra%20Design/Cloud%20Infra%20Design%2030K%20feet/Readme.md).

---

## ⚙️ Steps to Setup Listener Rules for Load Balancer ⚙️

### **Step 1: Create Target Group** 🖥️
1. Open the **Amazon EC2 console** at [AWS EC2 Console](https://console.aws.amazon.com/ec2/).
2. In the navigation pane, choose **Target Groups** and click on **Create Target Group**.

 ![image](https://github.com/user-attachments/assets/f95a951b-479b-40d0-ae5e-8e4d29a55f68)
  
3. Choose the target type: either **Instances** or **IP**.
![Screenshot 2024-10-09 100906](https://github.com/user-attachments/assets/ec4703e6-a285-44a4-ae90-ce894b9a8e0b)


4. Enter a target group name (e.g., `OTMS-Dev-TG-Attendance) and choose the appropriate **VPC**.
 ![Screenshot 2024-10-17 154808](https://github.com/user-attachments/assets/08578b3d-d168-4efc-b36b-e0d2a203cb1a)
  


  
5. Configure the **Health Check** settings and register the targets. Ensure the port is set to `default`.

![Screenshot 2024-10-17 154817](https://github.com/user-attachments/assets/f2b38985-8d02-4891-80d2-555257db7164)




6. Review the configuration and click **Create Target Group**.

### **Step 2: Add Listener Rules to Load Balancer** 🔄
1. Go to the **Load Balancers** section in the EC2 console and select your load balancer (`OTMS-Dev-ALB-Attendance`).
![Screenshot 2024-10-09 100308](https://github.com/user-attachments/assets/abf97acc-2882-4352-87f6-3a5d3dc0e958)

<img width="686" alt="image" src="https://github.com/user-attachments/assets/cd7a4b02-86e8-4075-b0a4-e7728285c930">


 
 2. .Choose the **Target Group** to forward the traffic to. Adjust the weights if using multiple target groups.
    
<img width="945" alt="image" src="https://github.com/user-attachments/assets/c3e4bc17-f144-4216-b6cb-bdc993316c1b">

![Screenshot 2024-10-17 155016](https://github.com/user-attachments/assets/1ffb81ee-68ec-4c48-9f86-dad2e5be434c)


   
3. Click on create LoadBalancer.

![Screenshot 2024-10-09 101326](https://github.com/user-attachments/assets/21c99bf4-82b2-4c0a-b933-c8ae5aa2e6fd)

---

## 📊 Output 
After setting up the listener rules, the load balancer will correctly distribute traffic as per your rules. Use the DNS endpoint of the load balancer to test the Attendance API.

![Screenshot 2024-10-09 171230](https://github.com/user-attachments/assets/70db2393-748f-4089-8a32-9970fa39c091)



---

## 🎯 Conclusion 
Configuring listener rules is essential for effective traffic management in AWS. By following this guide, you’ll ensure your Attendance API handles traffic efficiently, leading to improved performance and optimized resource utilization.

---


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---

## 📚 References 

| Description               | Link                                                                 |
| --------------------------| -------------------------------------------------------------------- |
| Documentation Template     | https://github.com/OT-MICROSERVICES/documentation-template/wiki     |
| Dev Infra Design           | https://github.com/CodeOps-Hub/Documentation/blob/main/...          |
| Listener Rules             | https://docs.aws.amazon.com/elasticloadbalancing/latest/application |

