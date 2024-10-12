# 🌐 Setup AWS Load Balancers - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 12-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of Load Balancers](#key-features-of-load-balancers)
4. [Benefits of Using Load Balancers](#benefits-of-using-load-balancers)
5. [Setup Load Balancers for DEV-Infra](#setup-load-balancers-for-dev-infra)
   - [External Load Balancer](#external-load-balancer)
   - [Internal Load Balancer](#internal-load-balancer)
   - [Attachment to Resources](#attachment-to-resources)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This document provides guidance on setting up **AWS Load Balancers** to distribute incoming traffic efficiently across multiple instances and services within a VPC. Load balancers help in optimizing resource usage, reducing latency, and ensuring high availability.

---

## 📖 Introduction
**AWS Load Balancers** play a crucial role in managing traffic for applications deployed within an AWS VPC. By evenly distributing incoming requests across multiple resources, load balancers enhance application resilience, scalability, and performance. Here, both **External** and **Internal Load Balancers** are configured to handle public and internal traffic, respectively.

---

## 🔑 Key Features of Load Balancers

- **Automatic Scaling**: Dynamically scales to handle varying loads, optimizing application performance and availability.
- **Health Checks**: Monitors the health of attached instances and routes traffic only to healthy instances.
- **Multi-Layer Load Balancing**: Supports load balancing across both the application (Layer 7) and network (Layer 4) layers.
- **Secure Traffic Management**: Integrates with AWS Security Groups for secure routing and manages SSL/TLS certificates.

---

## 🎯 Benefits of Using Load Balancers

- **Improved Resilience**: Balances traffic to reduce the load on individual instances, enhancing system resilience.
- **Increased Availability**: Redirects traffic to healthy instances, ensuring minimal downtime.
- **Optimized Resource Utilization**: Allows efficient utilization of resources by evenly distributing traffic.
- **Flexible Architecture**: Supports seamless integration with internal and external services, creating a scalable and secure infrastructure.

---

## 🛠 Setup Load Balancers for DEV-Infra

### External Load Balancer
1. Go to the **EC2 Dashboard** in the AWS Console.
2. Under **Load Balancing**, select **Load Balancers** and click **Create Load Balancer**.
3. Choose **Application Load Balancer** and set **Scheme** to **Internet-facing** for public access.
4. Attach this load balancer to the appropriate VPC and select the subnets associated with the public endpoints.
5. Configure **Listeners**:
   - Set up HTTP (port 80) and HTTPS (port 443) listeners to direct traffic to the **Frontend**, **Attendance**, **Employee**, and **Salary APIs**.
6. Define **Security Groups** for public access, allowing HTTP/HTTPS traffic from necessary IP ranges.

### Internal Load Balancer
1. From the **Load Balancers** section, create another **Application Load Balancer**.
2. Choose **Scheme** as **Internal** for routing traffic between applications within the VPC.
3. Attach to the VPC and select private subnets for internal communication.
4. Configure **Listeners**:
   - For example, configure HTTP (port 80) and HTTPS (port 443) listeners as needed for internal routing.
5. Define **Security Groups** for internal access, restricting traffic to only internal IP ranges and applications.

### Attachment to Resources
1. **Register Targets**: Under **Target Groups**, create and register EC2 instances for each application (Attendance, Employee, Salary APIs) and Frontend.
2. Attach the External Load Balancer to **Frontend, Attendance, Employee, and Salary APIs** for public traffic.
3. Attach the Internal Load Balancer to handle communication between **Frontend** and **backend services** for secure internal routing.

---

## 🔚 Conclusion

AWS Load Balancers offer an efficient solution to distribute incoming and internal traffic across instances and services within the VPC, ensuring resilience, scalability, and high availability for critical applications.

---

## 📚 References

| Reference                                | Link                                                                                                  |
|------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                        | [Amazon EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)                                |
| Load Balancing Basics                    | [What is Load Balancing?](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html)  |

---

## 📞 Contact Information

| Name             | Email                        |
|------------------|------------------------------|
| Komal Jaiswal    | komal.jaiswal.snaatak@mygurukulam.co    |

