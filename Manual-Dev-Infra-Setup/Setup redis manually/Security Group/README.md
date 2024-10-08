# 🌐 Setup Redis Manually AWS Security Groups - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 07-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of Security Groups](#key-features-of-security-groups)
4. [Benefits of Using Security Groups](#benefits-of-using-security-groups)
5. [Setup Security Groups for DEV-Infra](#setup-security-groups-for-dev-infra)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This document provides an overview and setup guide for **AWS Security Groups**. Security groups act as virtual firewalls for controlling inbound and outbound traffic to AWS resources, providing enhanced security and access control within a VPC.

---

## 📖 Introduction
**AWS Security Groups** are crucial components of AWS networking that define the allowed inbound and outbound traffic for your resources. They provide a way to control access to instances, load balancers, and other resources within your VPC, ensuring that only authorized traffic is allowed while denying all other traffic by default.

---

## 🔑 Key Features of Security Groups

- **Stateful**: Security groups are stateful, meaning that if you allow an incoming request from an IP, the response is automatically allowed, regardless of outbound rules.
- **Rule-Based**: Security groups use rules to define what traffic is allowed and what is blocked, which can be customized per resource.
- **Multiple Attachments**: A single security group can be attached to multiple instances, enabling easy management of access rules.
- **Dynamic Updates**: Changes to security group rules are applied immediately without downtime, allowing for rapid adjustments.

---

## 🎯 Benefits of Using Security Groups

- **Enhanced Security**: Provides a secure environment by controlling traffic at the instance level, reducing the attack surface.
- **Flexibility**: Allows users to easily modify rules and customize access controls based on changing requirements.
- **Simplified Management**: Centralizes management of access rules, making it easier to maintain and audit security policies.
- **Integration with AWS Services**: Works seamlessly with other AWS services, ensuring secure access to resources like RDS, ELB, and EC2.

---

## 🛠 Setup Security Groups for DEV-Infra

1. **Create a Security Group**:
   - Navigate to the **EC2 Dashboard** in the AWS Management Console.
   - Select **Security Groups** under **Network & Security** and click **Create Security Group**.
   - Name your security group and provide a description.

2. **Define Inbound Rules**:
   - Click on the **Inbound Rules** tab.
   - Click on **Edit inbound rules** and add rules as needed (e.g., allowing HTTP, HTTPS, or SSH access).
   - Specify the source IP ranges or security groups that are allowed to access your resources.

3. **Define Outbound Rules**:
   - Click on the **Outbound Rules** tab.
   - Click on **Edit outbound rules** and specify which traffic is allowed to leave the security group.

4. **Attach the Security Group**:
   - Attach the created security group to the desired EC2 instances, load balancers, or other resources within your VPC.

5. **Review and Modify as Necessary**:
   - Regularly review and update the security group rules based on changes in application requirements or security policies.

## Setup of Redis Manually-Security Group

![image](https://github.com/user-attachments/assets/8de8186e-deed-4b63-93e3-e3013f9a5700)
![image](https://github.com/user-attachments/assets/f4f929a4-e007-46c2-ace8-e08e9f2720a3)![image](https://github.com/user-attachments/assets/2218114c-946a-4f3e-9e3d-48196a8f9793)



---

## 🔚 Conclusion

AWS Security Groups provide a powerful mechanism for controlling access to resources in your VPC. By configuring security groups appropriately, you can enhance the security of your applications, limit exposure to threats, and simplify the management of access controls. Implementing security groups is essential for establishing a secure cloud environment that meets your organization’s security standards.

---

## 📚 References

| Reference                                   | Link                                                                                                  |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                           | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)                              |
| Security Groups                             | [What is a Security Group?](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html)  |

---

## 📞 Contact Information

| Name             | Email                        | Phone           |
|------------------|------------------------------|-----------------|
| Komal Jaiswal    | komal.jaiswal@example.com    | +1 (555) 123-4567 |
