
# Jenkins AWS Infrastructure 🚀



| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 24-09-2024         | 0.1        | Brij Singh   | Jenkins AWS Infrastructure   |

## 📑 Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Infrastructure Diagram](#infrastructure-diagram)
4. [Contact Information](#contact-information)
5. [References](#references)

***

## 📘 Introduction
This README explains how to set up Jenkins on Amazon Web Services (AWS) cloud infrastructure, including a diagram of the architecture and deployment details.

***

## ⚙️ Prerequisites

| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.    |

***

## 🛠️ Description
| Name           |  Description                                                      |
|----------------|----------------------------------------------------------------------|
|**User Access**| Users connect through the internet.|
|**Public Subnets & Security Groups**| Public components allow internet traffic, controlled by security rules.|
|**Private Components & NAT Gateway**| Private resources access the internet securely through a NAT gateway.|
|**Bastion Instances**| Provide secure access to private resources.|
|**VPCs (Virtual Private Clouds)**| Isolated networks for all components.|
|**Load Balancer & High Availability**| Distributes traffic to ensure the system stays online and performs well.|


## 🖼️ Infrastructure Diagram


***

## 📧 Contact Information

For any queries or further information, feel free to contact:

| 📛 Name       | ✉️ Email Address                    |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |

***

## 🔗 References

| Source                                                                                 | Description              |
| -------------------------------------------------------------------------------------- | ------------------------ |
| [Jenkins HA on AWS](https://aws.amazon.com/blogs/devops/jenkins-high-availability-and-disaster-recovery-on-aws/)           | Infrastructure Reference |
| [SCRUM-118 Jenkins HA Ref Doc](https://opstree-team-qa7417nu.atlassian.net/jira/software/projects/SCRUM/boards/1?issueParent=10059%2C10060%2C10061%2C10087&label=%23megha&selectedIssue=SCRUM-118)            | Jenkins HA Documentation |

"""


