# 🌐 Setup AWS Virtual Private Cloud (VPC) - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 06-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of a VPC](#key-features-of-a-vpc)
   - [Isolation](#isolation)
   - [Customization](#customization)
   - [Network Control](#network-control)
   - [Security](#security)
   - [Connectivity Options](#connectivity-options)
4. [Benefits of Using VPC](#benefits-of-using-vpc)
   - [Enhanced Security](#enhanced-security)
   - [Scalability](#scalability)
   - [High Availability](#high-availability)
5. [VPC Creation for DEV-Infra](#vpc-creation-for-dev-infra)
6. [Conclusion](#conclusion)

---

## 📜 Purpose
The purpose of this documentation is to provide an overview and guide to setting up an **AWS Virtual Private Cloud (VPC)**, a secure, isolated network environment within AWS. This documentation covers key VPC features, benefits, and provides steps for creating a VPC setup suitable for development infrastructure.

---

## 📖 Introduction
An **AWS Virtual Private Cloud (VPC)** is a secure, isolated section of the AWS cloud where users can define and manage their virtual networks. VPCs offer the flexibility to design a network environment with granular control over IP address ranges, subnets, route tables, and security settings, making it a powerful tool for hosting applications and data securely in the cloud.

---

## 🔑 Key Features of a VPC

- ### 🔒 Isolation
  Each VPC is logically isolated from other VPCs and the internet, ensuring security for workloads.

- ### ⚙️ Customization
  Users can customize network configurations, defining IP address ranges, creating subnets, and setting up route tables and gateways.

- ### 🔄 Network Control
  VPCs allow users to control both inbound and outbound network traffic at the subnet and instance levels.

- ### 🛡️ Security
  Enhanced security through **Security Groups** and **Network ACLs** that allow fine-grained traffic filtering.

- ### 🔗 Connectivity Options
  VPCs support **VPNs**, **direct connections**, **peering** with other VPCs, and **AWS VPC Endpoints** for secure connections to AWS services.

---

## 🎯 Benefits of Using VPC

- ### 🔐 Enhanced Security
  VPCs provide a secure environment to host applications, with options for both public and private subnets.

- ### 📈 Scalability
  VPCs can be expanded or modified as requirements change, supporting growing business needs.

- ### 🗄️ High Availability
  VPCs can span multiple **Availability Zones**, ensuring fault tolerance and redundancy.

---

## 🛠 VPC Creation for DEV-Infra

![image](https://github.com/user-attachments/assets/e5cbd626-0ec6-47cb-9e08-b099cfd5b824)
![image](https://github.com/user-attachments/assets/07923886-1f52-43eb-9058-7e74ac6ab740)


---

## 🔚 Conclusion

AWS VPC provides users with a powerful, flexible, and secure environment to create and manage their virtual networks within the AWS cloud. With VPC, users can control every aspect of their networking infrastructure, allowing them to deploy applications with the highest levels of security, scalability, and reliability. By leveraging VPC's robust features, businesses can build resilient cloud-based architectures that can adapt to evolving needs.
