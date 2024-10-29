# 🔒 ScyllaDB Security Group 


| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|---------------|--------------------|--------------------|-------------|-------------|-------------|
| Amit Nagar    | 16-10-2024     | Version 1     | Amit Nagar         | 28-10-2024         |     khushi        |     Akshay jain        |             


---

## 📑 Table of Contents

1. [📜 Introduction](#-introduction)
2. [🔍 Security Group Overview](#-security-group-overview)
3. [⬇️ Inbound Rules](#-inbound-rules)
4. [⬆️ Outbound Rules](#-outbound-rules)
5. [🛡️ Steps to Create Security Group for ScyllaDB](#-steps-to-create-security-group-for-scylladb)
6. [✅ Conclusion](#-conclusion)
7. [💡 Best Practices for Security](#-best-practices-for-security)
8. [📞 Contact Information](#-contact-information)
9. [🔗 References](#-references)

---


## 📜 Introduction
This document outlines the required security group configuration for ScyllaDB deployment. It focuses on ports and rules necessary to secure communication between ScyllaDB nodes and clients.

## 🔍 Security Group Overview

Security groups act as virtual firewalls that control inbound and outbound traffic for ScyllaDB nodes. They define rules that specify the allowed ports, protocols, and IP ranges for communication between nodes, clients, and external systems.

**Key Ports:**

| Port  | Protocol | Description                             |
|-------|----------|-----------------------------------------|
| 9042  | TCP      | CQL native transport (Client connections) |

---

## ⬇️ Inbound Rules

Inbound rules determine what traffic is allowed to reach the ScyllaDB instances. The following rules should be considered:

| Source IP/CIDR   | Port  | Protocol | Description                               |
|-------------------|-------|----------|-------------------------------------------|
| `<your-client-ip>`| 9042  | TCP      | Allow client connections to ScyllaDB.    |

---

## ⬆️ Outbound Rules

Outbound rules define the traffic allowed to leave the ScyllaDB instances. 
| Destination IP/CIDR  | Port  | Protocol | Description                              |
|-----------------------|-------|----------|------------------------------------------|
| `0.0.0.0/0`           | All   | All      | Allow all outbound traffic (customize as needed). |

---


## 🛡️ Steps to Create Security Group for ScyllaDB

1. **Log in to AWS Management Console**
   - Go to the [AWS Management Console](https://aws.amazon.com/console/).

2. **Navigate to the EC2 Dashboard**
   - In the Services menu, select **EC2**.

3. **Create a Security Group**
   - In the left sidebar, click on **Security Groups** under the **Network & Security** section.
   - Click the **Create Security Group** button.

  ![Screenshot from 2024-10-08 02-19-27](https://github.com/user-attachments/assets/7001318b-db7a-425e-8bc8-77766fcf72bf)

4. **Configure Security Group Settings**
   - **Name**: Enter `OTMS-Dev-SG-ScyllaDB`.
   - **Description**: Provide a description, e.g., "Security group for ScyllaDB in OTMS Development".
   - **VPC**: Select Dev VPC where you want to create this security group.
![Screenshot from 2024-10-08 10-56-52](https://github.com/user-attachments/assets/ed71c1da-3709-4868-a1aa-9f9007de6bf9)

![Screenshot from 2024-10-08 02-19-37](https://github.com/user-attachments/assets/2bb35ae0-f710-46bc-a654-01f9f46e8ab9)


5. **Set Inbound Rules**
   - Click on the **Inbound rules** tab.
   - Click on **Edit inbound rules**.
   - Add rules based on your requirements:
     - **Type**: Custom TCP Rule
     - **Protocol**: TCP
     - **Port Range**: 9042 (for ScyllaDB) 22(for ssh)
     - **Source**: Specify the security group  of the employee app , salary app 
   - Click on **Save rules**.
![image](https://github.com/user-attachments/assets/73d80f2c-4456-4709-a904-5c59b1ee21e9)

6. **Set Outbound Rules**
   - Click on the **Outbound rules** tab (defaults allow all traffic).
   - Optionally modify outbound rules as needed.

![Screenshot from 2024-10-24 12-19-15](https://github.com/user-attachments/assets/9501f06e-30ef-4ef8-8c8e-e59be2137b17)


7. **Review and Create**
   - Review the settings and click on the **Create security group** button.

---

## 💡 Best Practices for Security

- Limit access to known IP addresses for inbound rules to minimize exposure.
- Regularly review and update security group rules to reflect changes in the network environment.
- Use strong passwords and enable encryption for internal communication between nodes.
- Monitor logs for unauthorized access attempts.

---

## ✅ Conclusion

Creating a security group specifically for ScyllaDB enhances the security of your application by controlling access to the database. By following the outlined steps, you can effectively manage inbound and outbound traffic, ensuring that only authorized IP addresses can communicate with your ScyllaDB instance.


## 📞 Contact Information

| 👤 **Name**     | 📧 **Email Address**                                                   |
|-----------------|-----------------------------------------------------------------------|
| **Amit Nagar**  | [amit.nagar.snaatak@mygurukulam.com](mailto:amit.nagar.snaatak@mygurukulam.com) |

---

## 🔗 References

This section provides important resources and links for further reading on security groups and ScyllaDB configurations.

| 🌐 **Links**                                                                                     | 📄 **Descriptions**                                        |
|------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [📖 AWS Security Groups Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) | Comprehensive guide to understanding and configuring AWS Security Groups. |
| [📚 ScyllaDB Security Configuration](https://docs.scylladb.com/stable/architecture/security/) | Overview of security best practices and configurations for ScyllaDB. |
| [🔧 AWS Security Best Practices](https://aws.amazon.com/architecture/security-identity-compliance-best-practices/) | AWS best practices for securing applications and infrastructure. |

