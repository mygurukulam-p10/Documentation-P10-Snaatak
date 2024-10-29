# **Setup Listener Rules for Load Balancer (Employee API)**



| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 28-10-2024         |     khushi        |     Akshay jain        |             




---

## **Table of Contents** 📑
1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Steps to Setup Listener Rules for Load Balancer](#Steps-to-setup-Listener-Rules-for-Load-Balancer)
4. [Conclusion](#Conclusion)
5. [Contact Information](#Contact-Information)
6. [References](#References)

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
![Screenshot from 2024-10-24 13-02-44](https://github.com/user-attachments/assets/24f20315-8154-46d3-a740-57fd3d43f389)





6. Review the configuration and click **Create Target Group**.

### **Step 2: Add Listener Rules to Load Balancer** 🔄
1. Go to the **Load Balancers** section in the EC2 console and select your load balancer (`Dev-ALB`).
2. Click on Add rule
![Screenshot from 2024-10-24 13-38-03](https://github.com/user-attachments/assets/0176f6f5-a9e1-4db9-866c-8660acad1dbc)

![Screenshot from 2024-10-24 12-57-46](https://github.com/user-attachments/assets/4dbebc6a-a14d-4aca-be62-0c1986dcf287)

![Screenshot from 2024-10-24 12-57-53](https://github.com/user-attachments/assets/43cd24ba-4fb0-4754-b423-e4d42cf7d61d)

 
 2. .Choose the **Target Group** to forward the traffic to. Adjust the weights if using multiple target groups.
   ![Screenshot from 2024-10-09 16-50-31](https://github.com/user-attachments/assets/21117ca3-163a-4ed9-8d06-e7447d1f3833)

   ![Screenshot from 2024-10-24 12-58-07](https://github.com/user-attachments/assets/f89c2981-c527-4be1-a959-4fdf023a0769)

![Screenshot from 2024-10-24 12-58-33](https://github.com/user-attachments/assets/ccb40546-fd49-467f-b1e7-8c32d121c15b)

![Screenshot from 2024-10-24 12-58-47](https://github.com/user-attachments/assets/c1883e6d-bc2c-4d38-934c-484d7331045d)


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


