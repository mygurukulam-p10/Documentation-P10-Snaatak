# **Setup Listener Rules for Load Balancer (Employee API)**


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 09-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |



---

## **Table of Contents** 📑
1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Steps to Setup Listener Rules for Load Balancer](#Steps-to-setup-Listener-Rules-for-Load-Balancer)
4. [Output](#Output)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)

---

## **Introduction** 🌐
**Load balancing** in AWS ensures high availability and reliability by distributing network traffic across multiple resources. This guide will walk you through configuring listener rules for your Salary API to optimize traffic routing and performance using AWS Load Balancers.

---

## **Pre-requisites** ✔️
- **Access** to the AWS Management Console or AWS CLI with appropriate permissions.
- **Understanding** of your application's [network requirements](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Cloud%20Infra%20Design/Cloud%20Infra%20Design%2030K%20feet/Readme.md).

---

## **Steps to Setup Listener Rules for Load Balancer** ⚙️

### **Step 1: Create Target Group** 🖥️
1. Open the **Amazon EC2 console** at [AWS EC2 Console](https://console.aws.amazon.com/ec2/).
2. In the navigation pane, choose **Target Groups** and click on **Create Target Group**.

 ![image](https://github.com/user-attachments/assets/f95a951b-479b-40d0-ae5e-8e4d29a55f68)
  
3. Choose the target type: either **Instances** or **IP**.
![image](https://github.com/user-attachments/assets/8b565cbe-2b2d-4e06-8422-ede712b9ce8c)

4. Enter a target group name (e.g., `OTMS-Dev-TG-Employee) and choose the appropriate **VPC**.
 ![Screenshot from 2024-10-09 11-30-01](https://github.com/user-attachments/assets/0231c814-25e8-45c0-a157-14f498f7889f)


  
5. Configure the **Health Check** settings and register the targets. Ensure the port is set to `8080`.

![Screenshot from 2024-10-09 11-30-14](https://github.com/user-attachments/assets/40933414-90e8-41ea-a6fb-f4505332e28c)


6. Review the configuration and click **Create Target Group**.

### **Step 2: Add Listener Rules to Load Balancer** 🔄
1. Go to the **Load Balancers** section in the EC2 console and select your load balancer (`OTMS-Dev-ALB-Employee`).
![image](https://github.com/user-attachments/assets/93401816-7bbb-41a2-9dc0-5bff7fe272db)


![Screenshot from 2024-10-09 14-09-57](https://github.com/user-attachments/assets/6e33ea5b-8f99-49c6-bc98-f00626309e0e)

 
 2. .Choose the **Target Group** to forward the traffic to. Adjust the weights if using multiple target groups.
   ![Screenshot from 2024-10-09 16-50-31](https://github.com/user-attachments/assets/21117ca3-163a-4ed9-8d06-e7447d1f3833)

   
3. Click on create LoadBalancer.
---

## **Output** 📊
After setting up the listener rules, the load balancer will correctly distribute traffic as per your rules. Use the DNS endpoint of the load balancer to test the Salary API.

![Screenshot from 2024-10-09 16-56-20](https://github.com/user-attachments/assets/3719ef82-7494-40c0-a205-af12855005ff)


---

## **Conclusion** 🎯
Configuring listener rules is essential for effective traffic management in AWS. By following this guide, you’ll ensure your Salary API handles traffic efficiently, leading to improved performance and optimized resource utilization.

---

## **Contact Information** 📬

For any queries or further information, feel free to contact:

## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |

---

## **References** 📚

| Description               | Link                                                                 |
| --------------------------| -------------------------------------------------------------------- |
| Documentation Template     | https://github.com/OT-MICROSERVICES/documentation-template/wiki     |
| Dev Infra Design           | https://github.com/CodeOps-Hub/Documentation/blob/main/...          |
| Listener Rules             | https://docs.aws.amazon.com/elasticloadbalancing/latest/application |


