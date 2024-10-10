# 🌐 Setup Redis Manually on AWS - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 10-10-24   | Version 1 | Komal Jaiswal   | 10-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of Redis on AWS](#key-features-of-redis-on-aws)
4. [Benefits of Setting Up Redis on AWS](#benefits-of-setting-up-redis-on-aws)
5. [Setup Redis Instance on AWS](#setup-redis-instance-on-aws)
6. [Configuring Security Groups for Redis](#configuring-security-groups-for-redis)
7. [Conclusion](#conclusion)
8. [References](#references)
9. [Contact Information](#contact-information)

---

## 📜 Purpose
This document serves as a guide to manually setting up **Redis on AWS**. It provides step-by-step instructions for configuring a Redis instance and securing it using AWS Security Groups, ensuring controlled access to the Redis instance.

---

## 📖 Introduction
**Redis** is a high-performance, in-memory data structure store used for caching, session management, and message brokering. Running Redis on AWS provides scalability, security, and integration with other AWS services, making it an ideal choice for cloud-native applications.

---

## 🔑 Key Features of Redis on AWS

| Key Feature               | Description                                                                                         |
|---------------------------|-----------------------------------------------------------------------------------------------------|
| **In-Memory Storage**     | Redis stores data in memory for ultra-fast access.                                                |
| **Persistence**           | Allows for data durability with AOF (Append-Only File) and RDB (Redis Database) snapshotting.     |
| **Built-in Replication**   | Supports primary-replica configurations for high availability.                                     |
| **Flexible Data Types**   | Offers strings, lists, sets, hashes, and other data types to support various use cases.           |

---

## 🎯 Benefits of Setting Up Redis on AWS

| Benefit                     | Description                                                                                         |
|-----------------------------|-----------------------------------------------------------------------------------------------------|
| **Scalability**             | Easily scale vertically by upgrading instance types as your workload grows.                       |
| **Security**                | Integration with AWS security features, including Security Groups and VPCs, helps manage access and secure data. |
| **High Availability**       | AWS infrastructure enables reliable and redundant setups for Redis.                                 |
| **Ease of Integration**     | Redis on AWS works seamlessly with other AWS services like EC2, Lambda, and RDS.                   |

---

## 🛠 Setup Redis Instance on AWS

1. **Launch an EC2 Instance**:
   - Open the **EC2 Dashboard** in the AWS Management Console.
   - Select **Instances** and click **Launch Instances**.
   - Choose the Amazon Machine Image (AMI) based on your requirements (e.g., Amazon Linux or Ubuntu).
   - Select an instance type suitable for Redis (e.g., t2.micro for testing, larger instances for production).

2. **Instance Configuration**:
   - Configure **Network** and **Subnet** based on your VPC setup.
   - Assign an **Elastic IP** (optional) if you need a static IP address.

3. **Storage and Tags**:
   - Allocate sufficient **storage** as per your needs, and tag the instance for easy identification.

---

## 🔐 Configuring Security Groups for Redis

For detailed instructions on configuring security groups for Redis, please refer to the [Security Group POC](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Manual-Dev-Infra-Setup/Setup%20redis%20manually/Security%20Group).

---

## 🔚 Conclusion

Setting up Redis manually on AWS enables fine-tuned control over performance, security, and scalability. By configuring the Redis instance and securing it with AWS Security Groups, you can build a robust and secure caching solution for your applications.

---

## 📚 References

| Reference                                  | Link                                                                                                     |
|--------------------------------------------|----------------------------------------------------------------------------------------------------------|
| AWS Documentation on EC2                   | [EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)                                          |
| Redis Documentation                        | [Redis Documentation](https://redis.io/documentation)                                                    |

---

## 📞 Contact Information

| Name             | Email                                  |
|------------------|----------------------------------------|
| Komal Jaiswal    | komal.jaiswal.snaatak@mygurukulam.co   |

--- 
