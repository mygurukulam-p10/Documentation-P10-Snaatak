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

 ![image](https://github.com/user-attachments/assets/f95a951b-479b-40d0-ae5e-8e4d29a55f68)
  
3. Choose the target type: either **Instances** or **IP**.
![image](https://github.com/user-attachments/assets/8b565cbe-2b2d-4e06-8422-ede712b9ce8c)

4. Enter a target group name (e.g., `OTMS-Dev-Salary-TG) and choose the appropriate **VPC**.
 
![image](https://github.com/user-attachments/assets/0b320c47-b20e-426b-bb21-3572a0d0c94f)

  
5. Configure the **Health Check** settings and register the targets. Ensure the port is set to `8080`.

![image](https://github.com/user-attachments/assets/5faf012e-4736-49b4-a462-73d9f7bc8221)

6. Review the configuration and click **Create Target Group**.

![image](https://github.com/user-attachments/assets/8e194483-8ffc-44bb-ac25-be015f48cd67)

### **Step 2: Add Listener Rules to Load Balancer** 🔄
1. Go to the **Load Balancers** section in the EC2 console and select your load balancer (`OTMS-Dev-Salary-ALB`).
![image](https://github.com/user-attachments/assets/93401816-7bbb-41a2-9dc0-5bff7fe272db)

![image](https://github.com/user-attachments/assets/db927234-f1ed-4d8f-a265-673ea050919a)


2. Click on **Listeners** and select **Protocol Port HTTP:80** to add a new rule.
  
3. Define the **Name** and add any relevant **Tags**.
   ![image](https://github.com/user-attachments/assets/9fabb414-52a5-494e-9514-75af93144596)

![image](https://github.com/user-attachments/assets/fcce0547-520b-4ea9-a981-a2c992ee9b54)


---

## **Output** 📊
After setting up the listener rules, the load balancer will correctly distribute traffic as per your rules. Use the DNS endpoint of the load balancer to test the Salary API.

![image](https://github.com/user-attachments/assets/3581b0fe-1090-4a95-9071-b9514dbce1c0)

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

