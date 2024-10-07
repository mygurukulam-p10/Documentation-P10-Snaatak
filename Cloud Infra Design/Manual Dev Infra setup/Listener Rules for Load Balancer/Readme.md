# **Setup Listener Rules for Load Balancer (Salary API)**


| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 08-10-2024         | 0.1        | Brij Singh   | Listener Rules for Load Balancer            |


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
   
3. Choose the target type: either **Instances** or **IP**.
4. Enter a target group name (e.g., `Dev-salary-tg`) and choose the appropriate **VPC**.
   
5. Configure the **Health Check** settings and register the targets. Ensure the port is set to `8080`.
6. Review the configuration and click **Create Target Group**.

### **Step 2: Add Listener Rules to Load Balancer** 🔄
1. Go to the **Load Balancers** section in the EC2 console and select your load balancer (`Dev-ALB`).
2. Click on **Listeners** and select **Protocol Port HTTP:80** to add a new rule.
  
3. Define the **Name** and add any relevant **Tags**.
4. Set the **Path Condition** (e.g., `/item/*`) for traffic routing.
 
5. Choose the **Target Group** to forward the traffic to. Adjust the weights if using multiple target groups.
6. Assign a **Priority** for the rule and review all settings.
7. Once verified, click **Create Rule**.

---

## **Output** 📊
After setting up the listener rules, the load balancer will correctly distribute traffic as per your rules. Use the DNS endpoint of the load balancer to test the Salary API.

---

## **Conclusion** 🎯
Configuring listener rules is essential for effective traffic management in AWS. By following this guide, you’ll ensure your Salary API handles traffic efficiently, leading to improved performance and optimized resource utilization.

---

## **Contact Information** 📬

For any queries or further information, feel free to contact:

| 👨‍💻 Name | 📧 Email Address |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |

---

## **References** 📚

| Description               | Link                                                                 |
| --------------------------| -------------------------------------------------------------------- |
| Documentation Template     | https://github.com/OT-MICROSERVICES/documentation-template/wiki     |
| Dev Infra Design           | https://github.com/CodeOps-Hub/Documentation/blob/main/...          |
| Listener Rules             | https://docs.aws.amazon.com/elasticloadbalancing/latest/application |

