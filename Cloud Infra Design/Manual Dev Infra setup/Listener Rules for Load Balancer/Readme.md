
# ⚙️ Setup Listener Rules for Load Balancer (Salary API)

|
| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 03-10-2024         | 0.1        | Brij Singh   | Auto Scaling              |

---

## 📚 Table of Contents
1. [Introduction](#-introduction)
2. [Pre-requisites](#-pre-requisites)
3. [Steps to Setup Listener Rules](#-steps-to-setup-listener-rules)
   - [Step 1: Create Target Group](#step-1-create-target-group)
   - [Step 2: Add Listener Rule](#step-2-add-listener-rule)
4. [Output](#-output)
5. [Conclusion](#-conclusion)
6. [Contact Information](#-contact-information)
7. [References](#-references)

---

## 📖 Introduction

Load balancing in AWS is a process of distributing incoming network traffic across multiple servers to ensure high availability and optimal performance of applications. A **load balancer** acts as a single point of contact for clients, directing requests to healthy targets like EC2 instances.

This guide will walk you through the steps of setting up **listener rules** to route traffic to your target groups within an AWS load balancer.

---

## 🔧 Pre-requisites
* 🛠️ **Access** to the AWS Management Console or AWS CLI with the necessary permissions.
* 📄 **Understanding** of your application's 
---

## 🚀 Steps to Setup Listener Rules

### Step 1: Create Target Group
1. Open the **Amazon EC2 Console** at [https://console.aws.amazon.com/ec2/](https://console.aws.amazon.com/ec2/).
2. In the left navigation pane, click on `Target Groups`.
3. Choose **Create Target Group**.
4. Under `Target type`, select **Instances** for instance ID targets or **IP** for IP addresses.
5. Enter a target group name (e.g., `Dev-salary-tg`).
6. Choose a **VPC** (e.g., `Dev-VPC`) and provide a health check endpoint.
7. Keep the default configurations and click **Next**.
8. Register your targets (e.g., EC2 instances), specify port `8080`, and click **Register**.

---

### Step 2: Add Listener Rule

1. In the EC2 console, navigate to `Load Balancers`.
2. Click on the **Dev-ALB** load balancer.
3. Click on the `HTTP:80` listener.
4. Click **Add Rule**.
5. Define the rule's name and necessary tags.
6. Add a condition to specify the path (e.g., `/item/*`) and confirm.
7. Choose the target group(s) to forward traffic and assign weight if needed.
8. Set the rule priority (e.g., 1-50000) and leave gaps between numbers.
9. Review your configuration and click **Create**.

---

## 📊 Output



---

## 🏁 Conclusion

By following the steps outlined in this guide, you can set up **listener rules** for an AWS load balancer. This helps distribute traffic efficiently, ensuring your application's high availability and performance. AWS Load Balancer simplifies traffic management, offering a robust solution for scalable applications.

---

## 📧 Contact Information

For any queries or further information, feel free to contact:

| 👨‍💻 Name | 📧 Email Address |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |
---

---

## 📚 References

| Description              | Link                                                                 |
| ------------------------ | -------------------------------------------------------------------- |
| Documentation Template   | [Application Template](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |

| Listener Rules           | [AWS Documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-update-rules.html) |

