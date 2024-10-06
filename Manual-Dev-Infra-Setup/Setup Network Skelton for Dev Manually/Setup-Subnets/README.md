# 🌐 Setup AWS Subnets - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 06-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of Subnets](#key-features-of-subnets)
   - [Public Subnets](#public-subnets)
   - [Private Subnets](#private-subnets)
   - [Subnet Security](#subnet-security)
4. [Benefits of Using Subnets](#benefits-of-using-subnets)
   - [Enhanced Security](#enhanced-security)
   - [Efficient Network Segmentation](#efficient-network-segmentation)
5. [Subnet Creation for DEV-Infra](#subnet-creation-for-dev-infra)
   - [Public Subnets](#public-subnets-dev-infra)
   - [Private Subnets](#private-subnets-dev-infra)
6. [Conclusion](#conclusion)

---

## 📜 Purpose
The purpose of this documentation is to provide an overview and guide to setting up **AWS Subnets** as part of a Virtual Private Cloud (VPC) in AWS. This documentation covers key features, benefits, and steps for creating a subnet setup tailored for development infrastructure, featuring both public and private subnets.

---

## 📖 Introduction
An **AWS Subnet** is a logical subdivision of an AWS Virtual Private Cloud (VPC) that allows users to segment the network within their VPC. Subnets enable the organization of resources, control over IP address ranges, and isolation of sensitive workloads to enhance security and manageability.

---

## 🔑 Key Features of Subnets

- ### 🌐 Public Subnets
  Public subnets are directly accessible from the internet. Resources in public subnets can have public IP addresses, allowing them to interact with external systems. Commonly, public subnets host load balancers, web servers, and NAT gateways.

- ### 🔒 Private Subnets
  Private subnets are isolated from the internet and accessible only within the VPC. They are ideal for hosting internal services such as databases, application servers, and backend systems that do not need direct internet access.

- ### 🛡️ Subnet Security
  Enhanced security configurations include Network Access Control Lists (ACLs) and routing tables, which help manage traffic between subnets and control the inbound/outbound traffic at the subnet level.

---

## 🎯 Benefits of Using Subnets

- ### 🔐 Enhanced Security
  Subnets provide a secure way to organize and isolate resources within a VPC. Public subnets can facilitate external access while private subnets protect sensitive data and services from direct internet exposure.

- ### 🧩 Efficient Network Segmentation
  Subnets allow for better organization and control of network resources. By segmenting resources based on their function or level of exposure, subnets improve overall network performance and manageability.

---

## 🛠 Subnet Creation for DEV-Infra

In this section, we create a development environment infrastructure with two public subnets and three private subnets.

### 🌐 Public Subnets (DEV-Infra)

1. **Public Subnet 1**  
   - **Purpose**: Used for internet-facing resources such as load balancers and NAT gateways.
   - **CIDR**: 10.0.1.0/27
   - **Route Table**: Associated with a route table that directs traffic to the internet gateway.

![image](https://github.com/user-attachments/assets/041333c5-fd81-453f-a1d6-f06eec296ed1)

2. **Public Subnet 2**  
   - **Purpose**: Provides redundancy and load balancing for internet-facing applications.
   - **CIDR**: 10.0.1.32/28
   - **Route Table**: Also connected to the internet gateway for public access.
![image](https://github.com/user-attachments/assets/05cda3ec-c138-4b40-bfe7-50af957dc16b)


### 🔒 Private Subnets (DEV-Infra)

1. **Private Subnet 1 (OT-Dev-Frontend-Subnet)**  
   - **Purpose**: Hosts internal services like databases that do not need internet access.
   - **CIDR**: 10.0.1.48/28
   - **Route Table**: Configured to route traffic through the NAT gateway for secure outbound internet access.

![image](https://github.com/user-attachments/assets/3fc89211-935e-4206-ac62-a7b16e9f214d)


2. **Private Subnet 2 (OT-Dev-Application-Subnet)**  
   - **Purpose**: Provides redundancy for internal services.
   - **CIDR**: 10.0.1.64/27
   - **Route Table**: Also configured to use the NAT gateway.

![image](https://github.com/user-attachments/assets/385fa236-013e-4be3-ab50-8532c0bc37fe)

3. **Private Subnet 3 (OT-Dev-Database-Subnet)**  
   - **Purpose**: Used for additional backend services or application servers.
   - **CIDR**: 10.0.1.96/27
   - **Route Table**: Configured similarly to ensure secure access to the internet through the NAT gateway.

![image](https://github.com/user-attachments/assets/46194a66-a826-4408-afcd-c90c4614fbdb)

---

## 🔚 Conclusion

AWS Subnets provide a structured, secure, and flexible way to organize resources within a VPC. By dividing resources into public and private subnets, users can maintain high levels of security, control network traffic, and efficiently manage applications with different access requirements. This segmentation within AWS cloud infrastructure allows businesses to build scalable and resilient applications with ease.
