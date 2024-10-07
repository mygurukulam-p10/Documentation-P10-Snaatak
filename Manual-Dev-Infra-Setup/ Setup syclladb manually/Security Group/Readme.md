# 🔒 ScyllaDB Security Group 

---

## 📑 Table of Contents

1. [📜 Introduction](#-introduction)
2. [🔍 Security Group Overview](#-security-group-overview)
3. [⬇️ Inbound Rules](#-inbound-rules)
4. [⬆️ Outbound Rules](#-outbound-rules)
5. [💡 Best Practices for Security](#-best-practices-for-security)
6. [📞 Contact Information](#-contact-information)
7. [🔗 References](#-references)

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

Outbound rules define the traffic allowed to leave the ScyllaDB instances. You may use the following rule:

| Destination IP/CIDR  | Port  | Protocol | Description                              |
|-----------------------|-------|----------|------------------------------------------|
| `0.0.0.0/0`           | All   | All      | Allow all outbound traffic (customize as needed). |

---

## 💡 Best Practices for Security

- Limit access to known IP addresses for inbound rules to minimize exposure.
- Regularly review and update security group rules to reflect changes in the network environment.
- Use strong passwords and enable encryption for internal communication between nodes.
- Monitor logs for unauthorized access attempts.

---

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

