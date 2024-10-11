# 🌐 Setup AWS NAT Gateway, Internet Gateway, and Route Tables - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 06-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [NAT Gateway](#nat-gateway)
   - [Key Features of NAT Gateway](#key-features-of-nat-gateway)
   - [Benefits of Using NAT Gateway](#benefits-of-using-nat-gateway)
   - [NAT Gateway Setup for DEV-Infra](#nat-gateway-setup-for-dev-infra)
4. [Internet Gateway (IGW)](#internet-gateway-igw)
   - [Key Features of Internet Gateway](#key-features-of-internet-gateway)
   - [Benefits of Using Internet Gateway](#benefits-of-using-internet-gateway)
   - [Internet Gateway Setup for DEV-Infra](#internet-gateway-setup-for-dev-infra)
5. [Route Tables](#route-tables)
   - [Key Features of Route Tables](#key-features-of-route-tables)
   - [Benefits of Using Route Tables](#benefits-of-using-route-tables)
   - [Route Table Configuration for DEV-Infra](#route-table-configuration-for-dev-infra)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This document provides an overview and setup guide for **AWS NAT Gateway**, **Internet Gateway (IGW)**, and **Route Tables** as essential components for managing network traffic within a VPC. These components enable secure internet access, routing control, and network isolation for resources in both public and private subnets in a development infrastructure.

---

## 📖 Introduction
AWS VPC components like NAT Gateway, Internet Gateway, and Route Tables help manage network traffic and access in a secure, structured way. By leveraging these components, users can ensure seamless access control and data protection for both public-facing and internal resources within their VPC.

---

## 🔑 NAT Gateway

### Key Features of NAT Gateway

- **Outbound Internet Access**: Provides internet access for instances in private subnets without exposing them to inbound internet traffic.
- **Automatic Scaling**: Scales automatically within bandwidth limits based on demand.
- **High Availability**: Ensures fault tolerance when created in multiple Availability Zones.
- **Simplified Management**: AWS manages the infrastructure, reducing the need for manual setup and maintenance.

### 🎯 Benefits of Using NAT Gateway

- **Enhanced Security**: Allows private subnet resources to initiate internet connections without inbound exposure.
- **Cost Efficiency**: Minimizes the cost of maintaining NAT instances by using a managed solution.
- **Reliability**: Reduces downtime risks by providing high availability across multiple zones.

### 🛠 NAT Gateway Setup for DEV-Infra

1. **Create a NAT Gateway** in each required Availability Zone within your VPC.
2. **Associate NAT Gateways** with the public subnets, and update route tables to route traffic from private subnets through the NAT Gateway.
3. **Attach Elastic IP Addresses** to each NAT Gateway for internet access.

![image](https://github.com/user-attachments/assets/6edcd413-0c35-4f26-975c-f9252ec7a9fd)
![image](https://github.com/user-attachments/assets/424be3f3-f7da-4203-b35d-1126c7d3e003)



---

## 🌐 Internet Gateway (IGW)

### Key Features of Internet Gateway

- **Internet Access**: Provides a target in the route table to enable instances in public subnets to access the internet.
- **Bidirectional Traffic**: Supports both inbound and outbound internet traffic.
- **Scalability**: Scales horizontally to meet traffic demands without user intervention.
- **Direct Connectivity**: Allows direct internet connectivity for instances in public subnets.

### 🎯 Benefits of Using Internet Gateway

- **Public Access Control**: Enables secure, controlled internet access for public subnet resources.
- **Simplified Configuration**: Eliminates the need for complex routing configurations to connect public subnets to the internet.
- **Scalability and Reliability**: Provides a robust, scalable gateway for VPC internet connectivity.

### 🛠 Internet Gateway Setup for DEV-Infra

1. **Create an Internet Gateway** and attach it to your VPC.
2. **Configure Route Tables** to associate the IGW with public subnets, allowing instances to access the internet.
3. **Set Security Group Rules** for instances in public subnets to permit necessary inbound and outbound traffic.

![image](https://github.com/user-attachments/assets/160fc938-57c4-4abd-88c9-5e14e582dff3)
![image](https://github.com/user-attachments/assets/b435bdcc-a75c-4c7a-87d8-9655b6b0a805)

---

## 📜 Route Tables

### Key Features of Route Tables

- **Routing Control**: Directs traffic between subnets, the internet, and other VPCs.
- **Custom Routes**: Supports custom routes for specific use cases, including VPC peering and direct connections.
- **Traffic Segmentation**: Separates routes based on subnet type (public/private) for structured network traffic flow.
- **Failover Support**: Can be configured to handle traffic failover across routes in case of network outages.

### 🎯 Benefits of Using Route Tables

- **Traffic Management**: Provides granular control over routing paths for resources in the VPC.
- **Network Isolation**: Ensures secure separation between private and public subnet traffic.
- **Flexibility**: Allows adding multiple routes to support complex architectures, including VPC peering and on-premises connections.

### 🛠 Route Table Configuration for DEV-Infra

1. **Create and Associate Route Tables**:
   - Associate a route table with each subnet based on its access needs.

   - **Public Subnets**: Add routes to direct internet-bound traffic to the Internet Gateway.

![image](https://github.com/user-attachments/assets/f82b1332-c5c9-4a54-9737-d57f4de08c4b)
![image](https://github.com/user-attachments/assets/b0e7c82f-b09a-4adf-9924-71c9d1cb9809)
![image](https://github.com/user-attachments/assets/094fe574-db2c-46eb-851b-0c7803253279)
![image](https://github.com/user-attachments/assets/bc5772c7-36c9-47f8-9d92-afdf3e99fe9c)




   - **Private Subnets**: Add routes to direct internet-bound traffic through the NAT Gateway for secure outbound access.

![image](https://github.com/user-attachments/assets/883d3ddc-4e73-4581-86d8-d19d1d98c513)
![image](https://github.com/user-attachments/assets/7316fcff-98bb-4061-b80d-b216dc5d23e8)
![image](https://github.com/user-attachments/assets/296b736f-ec30-430b-8e3f-6688eec93416)
![image](https://github.com/user-attachments/assets/e9618d35-c04d-4cab-8c93-08f17fc42b45)



2. **Set Default Routes** as required for public and private traffic within the VPC like IGW for Public and NAT for Private

---

## 🔚 Conclusion

NAT Gateways, Internet Gateways, and Route Tables are essential components in AWS VPCs for managing network traffic and providing secure access controls. By configuring these components, users can control internet access, direct traffic efficiently, and maintain a secure network environment suitable for scalable cloud applications. Proper setup of these resources ensures high availability, robust security, and controlled connectivity within the AWS ecosystem.

---

## 📚 References

| Reference                                   | Link                                                                                                  |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                           | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)                              |
| NAT Gateway                                 | [What is a NAT Gateway?](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-gateway.html)    |
| Internet Gateway                            | [What is an Internet Gateway?](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html) |
| Route Tables                                | [Route Tables in Amazon VPC](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html) |

---

## 📞 Contact Information

| Name             | Email                        |
|------------------|------------------------------|
| Komal Jaiswal    | komal.jaiswal.snaatak@mygurukulam.co|
