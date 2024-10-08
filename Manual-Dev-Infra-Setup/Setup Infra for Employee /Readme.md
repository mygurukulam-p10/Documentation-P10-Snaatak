# Employee API Instance Setup 🚀


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 9-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |


---

## 📑 Table of Contents
1. [📝 Introduction](#-introduction)
2. [📊 EC2 Instance Types](#-ec2-instance-types)
3. [🌟 Why Use AWS EC2 Instance](#-why-use-aws-ec2-instance)
4. [⚙️ Pre-requisites](#-pre-requisites)
5. [🛠  Steps to Launch an EC2 Instance](#-steps-to-launch-an-ec2-instance)
6. [💡 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

---

## 📝 Introduction
In this document, we will create a new **Amazon EC2 instance** running, and configure it.

### What is an EC2 Instance?
An instance in Amazon EC2 is essentially a virtual server within the AWS cloud, allowing users to manage their applications with flexibility and scalability. Instances are launched from **Amazon Machine Images (AMIs)**, serving as templates containing the OS and software configurations. You can start, stop, or resize instances as needed.

---

## 📊 EC2 Instance Types

| Instance Type           | Description                                                                 | Common Use Cases                                                                            |
|-------------------------|-----------------------------------------------------------------------------|-------------------------------------------------------|
| **General Purpose**      | Balanced resources for diverse workloads.                                   | Web hosting, dev environments                                                               |
| **Compute Optimized**    | High-performance processors for heavy compute workloads.                    | Scientific modeling, big data processing                                                     |
| **GPU Instances**        | Optimized for graphics-intensive applications.                              | Game development, machine learning                                                          |
| **Memory Optimized**     | High-performance memory for data-heavy applications.                        | Real-time analytics, big data                                                                |
| **Storage Optimized**    | Optimized for high-speed storage applications.                              | Data processing, NoSQL databases                                                             |
| **Micro Instances**      | Low-cost instances for low-throughput applications.                         | Low-traffic web servers, testing environments                                                |

---

## 🌟 Why Use AWS EC2 Instance?

| Feature                   | Description                                                                                     |
|---------------------------|-------------------------------------------------------------------------------------------------|
| **Multi-OS Support**       | Runs various operating systems including Linux, Windows, and more.                              |
| **Elastic Block Storage**  | Persistent block-level storage for your instance that can be resized.                           |
| **Elastic IP**             | Static IP address that can be easily associated or reassigned to instances.                     |
| **Amazon CloudWatch**      | Real-time monitoring and alerts for resource usage and performance.                             |
| **Bare-metal Instances**   | Direct access to hardware without virtualization overhead.                                      |
| **Pause and Resume**       | Pause instances to save costs, and resume when required.                                        |

---

## ⚙️ Pre-requisites
- Access to **AWS Management Console** or **AWS CLI**.
- Knowledge of your application’s [network requirements](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Cloud%20Infra%20Design/Cloud%20Infra%20Design%2030K%20feet/Readme.md).

---

## 🛠 Steps to Launch an EC2 Instance

1. **Login** to your [AWS Console](https://aws.amazon.com/console/).  
2. Navigate to the **EC2 Dashboard**.
 ![image](https://github.com/user-attachments/assets/32eaeb3a-f4a9-421e-a983-c4870fa38ca3)
 
3. Select `Launch Instance`.  
4. Enter a **name** for the instance under **Name and Tags**.
![Screenshot from 2024-10-09 01-53-54](https://github.com/user-attachments/assets/29a4e440-ccd2-40f8-be34-476947d0f5eb)


5. Select the appropriate **Amazon Machine Image (AMI)** (e.g., Amazon Linux).
![Screenshot from 2024-10-09 01-55-12](https://github.com/user-attachments/assets/8a0effc3-9b29-445e-bd74-27e065f18b75)


 
6. Choose your **instance type**, key pair, and network settings.
 ![image](https://github.com/user-attachments/assets/776a6465-ac87-4767-89a9-2ae1bf7f730a)
 
7. Configure **security group settings** for your instance.
 ![Screenshot from 2024-10-09 02-00-57](https://github.com/user-attachments/assets/bd51abcb-6f02-4b95-bf5d-382554e2df3d)


8 Finally, click **Launch** and your instance will be up shortly! 🎉
![Screenshot 2024-10-08 162041](https://github.com/user-attachments/assets/71f8b640-b50b-4bb8-8208-aca6bb47b308)
![Screenshot from 2024-10-09 02-01-48](https://github.com/user-attachments/assets/e1713398-4970-4ba3-8732-48d1b2e4161f)


NOTE : After successfully launching the instance follow this Employee API Setup Document. [here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/OT%20MS%20Understanding/Employee/Setup%20and%20run%20the%20App%20for%20POC%20)

## 💡 Conclusion

Amazon EC2 provides versatile, scalable, and cost-efficient instances, enabling users to deploy applications quickly. The instances come with a wide array of options for OS, storage, and networking, making it a reliable choice for any cloud computing needs.

---

## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |

---

## 📚 References

- [AWS EC2 Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html)
- [Cloud Infra Design](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/Cloud%20Infra%20Design/Cloud%20Infra%20Design%2030K%20feet/Readme.md). 



