
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
This README provides an overview of the AWS infrastructure setup for Jenkins. It includes a detailed architecture diagram and outlines how Jenkins is deployed within the AWS ecosystem.

***

## ⚙️ Prerequisites

| Tool                  | Description                                  |
|-----------------------|----------------------------------------------|
| AWS Management Console | Required for provisioning AWS resources.    |

***

## 🛠️ Description

- Users access the environment through the internet.
- Traffic is routed through public subnets and security groups.
- Private components access the internet via a NAT gateway.
- Bastion instances provide secure access to private resources.
- All components are deployed within Virtual Private Clouds (VPCs).
- Load balancer ensures high availability (HA).

***

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


