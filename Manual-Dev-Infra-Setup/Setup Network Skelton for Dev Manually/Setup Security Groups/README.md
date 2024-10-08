# 🌐 Setup AWS Security Groups - Documentation

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
   - [Inbound Rules](#inbound-rules)
   - [Outbound Rules](#outbound-rules)
   - [Attachment to Resources](#attachment-to-resources)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This document provides a guide for setting up and configuring **AWS Security Groups** to enhance network security within a VPC. Security groups serve as virtual firewalls, controlling access to resources by defining inbound and outbound rules that specify allowed IP addresses, protocols, and ports.

---

## 📖 Introduction
**AWS Security Groups** are essential for controlling access to EC2 instances and other resources within an AWS VPC. Each security group acts as a firewall that filters incoming and outgoing traffic based on user-defined rules. By configuring security groups, users can effectively limit access, reducing the attack surface and protecting sensitive data and applications.

---

## 🔑 Key Features of Security Groups

- **Stateful Filtering**: Security groups are stateful, allowing return traffic for inbound rules without explicitly defining outbound rules.
- **Flexible Rule Creation**: Users can create custom rules to control IP ranges, protocols, and ports for both inbound and outbound traffic.
- **Multiple Attachments**: A single security group can be attached to multiple instances, allowing centralized control over access.
- **Immediate Rule Application**: Changes to security group rules are applied in real-time without restarting instances.

---

## 🎯 Benefits of Using Security Groups

- **Enhanced Security**: Provides an additional layer of security, controlling traffic at the instance level within a VPC.
- **Simplified Management**: Centralizes access control, making it easier to manage and audit security policies.
- **Improved Flexibility**: Allows for granular control over which IPs and networks have access, ensuring only trusted sources are allowed.
- **Automatic Adaptation**: Security group rules apply immediately to all attached instances, ensuring seamless updates to access policies.

---

## 🛠 Setup Security Groups for DEV-Infra

### Inbound Rules
1. Navigate to the **EC2 Dashboard** in the AWS Console.
2. Under **Network & Security**, select **Security Groups** and click **Create Security Group**.
3. Set a **Name** and **Description** for the security group.
4. Under **Inbound Rules**, define rules for allowing inbound traffic:
   - For example, allow SSH (port 22) from a specific IP range or HTTP/HTTPS access for web servers.
   - Specify IP ranges (CIDR blocks) or use other security groups as sources.

### Outbound Rules
1. Click on the **Outbound Rules** tab within the security group.
2. Define outbound rules as needed (e.g., allowing outbound HTTP/HTTPS traffic).
   - For example, allow all traffic (default) or restrict traffic to specific IPs or protocols.

### Attachment to Resources
1. Attach the security group to desired EC2 instances, load balancers, or databases within your VPC:
   - Under the **EC2 Instances** page, select an instance, and click **Actions** > **Networking** > **Change Security Groups**.
   - Choose the newly created security group from the list and apply it to the instance.

![image](https://github.com/user-attachments/assets/1372ece7-e765-4820-8954-badb7d9da96f)

---

## 🔚 Conclusion

AWS Security Groups provide a robust solution for managing access to AWS resources, enhancing overall network security, and allowing granular control over inbound and outbound traffic. With these controls, users can protect sensitive applications and data, ensuring a secure, scalable, and manageable cloud environment.

---

## 📚 References

| Reference                                   | Link                                                                                                  |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                           | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)                               |
| Security Groups                             | [What is a Security Group?](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-security-groups.html)  |

---

## 📞 Contact Information

| Name             | Email                        |
|------------------|------------------------------|
| Komal Jaiswal    | komal.jaiswal@example.com    |

