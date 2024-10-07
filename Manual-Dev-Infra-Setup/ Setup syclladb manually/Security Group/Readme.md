# 🔒 ScyllaDB Security Group and Rules PoC

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

| 🌐 **Links**                                                                                 | 📄 **Descriptions**                                        |
|---------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [📘 ScyllaDB Documentation](https://docs.scylladb.com/)                                      | Official ScyllaDB documentation.                           |
| [🔧 ScyllaDB Installation Guide](https://docs.scylladb.com/stable/operating-scylla/procedures/install/install-ubuntu.html) | Official installation guide for Ubuntu.                   |
| [🎓 ScyllaDB University](https://university.scylladb.com/)                                   | Free online courses to get started with ScyllaDB.          |

---

