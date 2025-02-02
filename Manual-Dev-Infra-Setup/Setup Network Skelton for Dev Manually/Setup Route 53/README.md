# 🌐 Setup AWS Route 53 - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 26-10-24   | Version 1 | Komal Jaiswal   | 26-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of Route 53](#key-features-of-route-53)
4. [Benefits of Using Route 53](#benefits-of-using-route-53)
5. [Setup Route 53 for DEV-Infra](#setup-route-53-for-dev-infra)
   - [DNS Management](#dns-management)
   - [Health Checks](#health-checks)
   - [Hosted Zones and Records](#hosted-zones-and-records)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This document provides a guide for setting up and configuring **AWS Route 53** to manage domain name resolution, route traffic, and perform health checks. Route 53 is a scalable and highly available DNS service that connects requests to applications hosted on AWS or external resources.

---

## 📖 Introduction
**AWS Route 53** is a fully managed DNS service that enables users to connect user requests to AWS-hosted or external resources. By configuring Route 53, users can route end-user traffic reliably and configure domain management, health checks, and DNS failover to ensure high availability and resiliency.

---

## 🔑 Key Features of Route 53

- **Domain Registration**: Allows users to register and manage domain names directly within AWS.
- **Health Checks and Failover**: Monitors the health of resources and reroutes traffic to healthy endpoints.
- **Global DNS**: Provides a scalable DNS service with low-latency routing and geolocation-based traffic control.
- **DNS Management**: Supports creating and managing DNS records, including A, CNAME, and MX records.

---

## 🎯 Benefits of Using Route 53

- **Improved Availability**: Automatically redirects traffic away from unhealthy endpoints, maintaining high availability.
- **Scalable DNS**: Provides a scalable solution to handle DNS requests for applications of any scale.
- **Enhanced Security**: Allows integration with VPC and private DNS for secure routing within a private network.
- **Flexible Traffic Management**: Enables routing policies such as latency-based, geolocation-based, and weighted routing.

---

## 🛠 Setup Route 53 for DEV-Infra

### DNS Management
1. Go to the **Route 53 Dashboard** in the AWS Console.
2. Under **DNS Management**, click **Create Hosted Zone** and define the **Domain Name** for the environment (e.g., `example.com`).
3. Select **Public Hosted Zone** for domains that need to be accessible over the internet or **Private Hosted Zone** for internal use within a VPC.

### Health Checks
1. Navigate to **Health Checks and Monitoring** in the Route 53 Console.
2. Click **Create Health Check** and specify the **Endpoint** (IP address, domain name, or URL) to monitor.
   - Configure the protocol (HTTP/HTTPS) and specify the port.
3. Set up **Failover** options to reroute traffic based on health check status to maintain high availability.

### Hosted Zones and Records
1. Under **Hosted Zones**, select the hosted zone created for your domain.
2. Click **Create Record** and configure the following common records:
   - **A Record**: Maps a domain to an IP address.
   - **CNAME Record**: Maps a domain alias to another domain name.
   - **MX Record**: Defines mail servers for email routing.
3. Attach these records to Route 53 DNS to route traffic to appropriate EC2 instances or Load Balancers.

#### Route 53 Setup
![image](https://github.com/user-attachments/assets/25fb1c1d-a3ef-409e-99dd-ac47731c8d5b)
![image](https://github.com/user-attachments/assets/bf7ef1d1-5c7d-4928-83a1-d75d5f8f5b81)

![image](https://github.com/user-attachments/assets/48ae8b3d-37d6-4af4-8e24-fed2fe3a5a2d)
![image](https://github.com/user-attachments/assets/5e972d57-b964-480f-baa2-47942d9e5fed)
![image](https://github.com/user-attachments/assets/02872825-11a1-4db0-9e56-f2e73236f3e6)


---

## 🔚 Conclusion

AWS Route 53 provides a robust solution for managing DNS within the AWS ecosystem, supporting domain registration, traffic routing, and health checks to enhance the availability and resilience of applications. By integrating Route 53, users can improve application performance and ensure secure, reliable DNS management.

---

## 📚 References

| Reference                                   | Link                                                                                                  |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                           | [Amazon Route 53 Documentation](https://docs.aws.amazon.com/route53/index.html)                      |
| Route 53 Health Checks                      | [What are Health Checks?](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html) |

---

## 📞 Contact Information

| Name             | Email                        |
|------------------|------------------------------|
| Komal Jaiswal    | komal.jaiswal.snaatak@mygurukulam.co    |

