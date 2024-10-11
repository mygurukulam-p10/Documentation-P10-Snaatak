# 🌐 Setup AWS Security Groups - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 11-10-24       |                |                |                |

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

#### Open VPN
![image](https://github.com/user-attachments/assets/d0f52d6c-5bd7-4474-b9c5-1fbc1e9066af)
![image](https://github.com/user-attachments/assets/043ce987-40e7-4573-a46e-fbe65fbdd060)

#### ALB - SG
![image](https://github.com/user-attachments/assets/8fd53e57-e4de-4d2d-a480-8a5aa26003ae)
![image](https://github.com/user-attachments/assets/763a0001-0f95-460b-8b54-dd821c9b6952)

#### Frontend-SG
![image](https://github.com/user-attachments/assets/6fa23dc4-1ab7-4440-a78b-0cc988b15845)
![image](https://github.com/user-attachments/assets/1b4eaccb-8347-445b-9761-3c38aff0857d)

#### Attendance- SG
![image](https://github.com/user-attachments/assets/76f9b88a-77d9-4149-908c-410db4467eb7)
![image](https://github.com/user-attachments/assets/f456153d-788f-4a31-8688-f8e3a00d1e65)


#### Employee-SG
![image](https://github.com/user-attachments/assets/8291919e-6ea8-4f20-85c9-7779b5a88751)
![image](https://github.com/user-attachments/assets/d2b4cb3b-ab77-4bd7-aef2-d5b726ae3fc3)

#### Salary-SG
![image](https://github.com/user-attachments/assets/4c7bf117-27a7-46f7-8d88-bceb5907398e)
![image](https://github.com/user-attachments/assets/2611e1ae-d53a-4341-806f-19678ca52e48)

#### Redis-SG
![image](https://github.com/user-attachments/assets/fe31d460-f87e-4ba2-b5ee-83c707b15cc4)
![image](https://github.com/user-attachments/assets/971293cc-5ce8-4e07-8a10-8e4aa84628e3)

#### Postgres-SG
![image](https://github.com/user-attachments/assets/efee1411-8006-4960-9c8f-d1801ca89b3b)
![image](https://github.com/user-attachments/assets/2d8c2556-a070-4e36-8433-c3c145864cf1)

#### ScyllaDB-SG
![image](https://github.com/user-attachments/assets/f90559b3-aab1-4c63-b88d-ecb272cda118)
![image](https://github.com/user-attachments/assets/44dc019e-8c8e-4df2-a4ec-09cda69f5426)

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
| Komal Jaiswal    | komal.jaiswal.snaatak@mygurukulam.co    |

