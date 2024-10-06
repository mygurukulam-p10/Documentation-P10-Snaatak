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
   - **CIDR**: Specify the CIDR block for this subnet.
   - **Route Table**: Associated with a route table that directs traffic to the internet gateway.

2. **Public Subnet 2**  
   - **Purpose**: Provides redundancy and load balancing for internet-facing applications.
   - **CIDR**: Specify the CIDR block for this subnet.
   - **Route Table**: Also connected to the internet gateway for public access.

### 🔒 Private Subnets (DEV-Infra)

1. **Private Subnet 1**  
   - **Purpose**: Hosts internal services like databases that do not need internet access.
   - **CIDR**: Specify the CIDR block for this subnet.
   - **Route Table**: Configured to route traffic through the NAT gateway for secure outbound internet access.

2. **Private Subnet 2**  
   - **Purpose**: Provides redundancy for internal services.
   - **CIDR**: Specify the CIDR block for this subnet.
   - **Route Table**: Also configured to use the NAT gateway.

3. **Private Subnet 3**  
   - **Purpose**: Used for additional backend services or application servers.
   - **CIDR**: Specify the CIDR block for this subnet.
   - **Route Table**: Configured similarly to ensure secure access to the internet through the NAT gateway.

---

## 🔚 Conclusion

AWS Subnets provide a structured, secure, and flexible way to organize resources within a VPC. By dividing resources into public and private subnets, users can maintain high levels of security, control network traffic, and efficiently manage applications with different access requirements. This segmentation within AWS cloud infrastructure allows businesses to build scalable and resilient applications with ease.
