# 🌐 Setup AWS Load Balancers - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 21-10-24       |                |                |                |

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

### Internet Facing Load Balancer
1. Go to the **EC2 Dashboard** in the AWS Console.
![image](https://github.com/user-attachments/assets/fb03eddb-7136-4b74-967c-f383469e91d8)

2. Under **Load Balancing**, select **Load Balancers** and click **Create Load Balancer**.
![image](https://github.com/user-attachments/assets/85a1f94e-f041-451b-892f-7e7e7ef580ae)

3. Choose **Application Load Balancer** and set **Scheme** to **Internet-facing** for public access.

![image](https://github.com/user-attachments/assets/7643987f-29f4-48f2-878a-956a721c526a)

![image](https://github.com/user-attachments/assets/cea1faea-0c15-4955-b3fa-437b6bcf8ca6)

4. Attach this load balancer to the appropriate VPC and select the subnets associated with the public endpoints.

![image](https://github.com/user-attachments/assets/0e42169c-dfdf-43ed-a844-8a661a855ff9)

5. Configure **Listeners**:
   - Set up HTTP (port 80) and HTTPS (port 443) listeners to direct traffic to the **Frontend**, **Attendance**, **Employee**, and **Salary APIs**.
![image](https://github.com/user-attachments/assets/6b3507d6-cda5-4e49-a720-d0bdcb2fb836)
![image](https://github.com/user-attachments/assets/4f4974da-950d-41aa-a552-474a622dfc39)
![image](https://github.com/user-attachments/assets/120834ea-ee13-481e-98a3-65092d995995)



### Internal Load Balancer
1. From the **Load Balancers** section, create another **Application Load Balancer**.
![image](https://github.com/user-attachments/assets/78aeade0-8f25-4892-ad0c-20b8159e73b0)

2. Choose **Scheme** as **Internal** for routing traffic between applications within the VPC.
![image](https://github.com/user-attachments/assets/f201504b-89f0-4413-bb66-72b5a1e503c4)

3. Attach to the VPC and select private subnets for internal communication.
![image](https://github.com/user-attachments/assets/74dd09b9-a2ec-4c7c-b184-c8d6373278df)

4. Configure **Listeners**:
   - For example, configure HTTP (port 80) and HTTPS (port 443) listeners as needed for internal routing.
![image](https://github.com/user-attachments/assets/47fcc4a3-c143-4eb9-811e-8d20235b2fa1)

![image](https://github.com/user-attachments/assets/8eff28b1-bbdf-4a89-9000-cf2925606c09)


### Attachment to Resources
1. **Register Targets**: Under **Target Groups**, create and register EC2 instances for each application (Attendance, Employee, Salary APIs) and Frontend.
![image](https://github.com/user-attachments/assets/82340b01-c187-46cb-a3d7-135318273ce0)
![image](https://github.com/user-attachments/assets/d4fc8155-6baf-4994-8234-627cf52b62f5)
![image](https://github.com/user-attachments/assets/d00bbc7d-57f8-4fd3-ba10-9d2e9559555c)
![image](https://github.com/user-attachments/assets/c57214ac-829e-48b7-bceb-538d179c387b)
![image](https://github.com/user-attachments/assets/09bc526d-6794-40b8-917f-eb8268dab91e)
![image](https://github.com/user-attachments/assets/578f398c-946e-44c1-ad79-7f48ea0e6c32)


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

