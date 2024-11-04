# Attendance API Security Group Setup (Terraform)

| **Author**       | **Date**   | **Version** | **Reviewed By (L0)** | **Reviewed By (L1)** | **Reviewed By (L2)** |
|------------------|------------|-------------|-----------------------|-----------------------|-----------------------|
| Amit Nagar       | 05-11-24   | 1.0         | -                     | -                     | -                     |


---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features](#key-features)
4. [Benefits](#benefits)
5. [Steps for Security Group Setup](#steps-for-security-group-setup)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

### 🎯 Purpose
This README provides a guide for setting up a Security Group in AWS using Terraform, specifically for securing the Attendance API, with controlled access to the API resources.

### 📖 Introduction
The Security Group acts as a virtual firewall that controls inbound and outbound traffic for AWS resources. This configuration is specifically tailored to securely manage access to the Attendance API within a Virtual Private Cloud (VPC).

---

## 🔑 Key Features

| **Feature**               | **Description**                                                       |
|---------------------------|-----------------------------------------------------------------------|
| **Controlled Access**     | Allows only specified traffic, securing the Attendance API.          |
| **Granular Rules**        | Configure precise inbound and outbound rules for API access.         |
| **Flexible Management**   | Easily modify rules to accommodate changing security requirements.    |
| **Integrated with VPC**   | Ensures the Security Group is scoped within the defined VPC.         |

---

## 🏆 Benefits

| **Benefit**                     | **Description**                                                               |
|---------------------------------|-------------------------------------------------------------------------------|
| **Enhanced Security**           | Controls access to resources by restricting IP ranges and protocols.          |
| **Ease of Management**          | Managed through Terraform, making updates easy and trackable.                 |
| **Compliance Ready**            | Helps meet security compliance requirements by limiting access.               |
| **Scalable**                    | Supports new rules for growing infrastructure needs.                          |

---

## 🛠 Steps for Security Group Setup

### Step 1: Initialize the Terraform Directory
- Run `terraform init` to prepare the directory and download required providers.

### Step 2: Format the Terraform Code
- Use `terraform fmt` to format and organize the Terraform configuration files.

### Step 3: Validate the Configuration
- Run `terraform validate` to check for syntax or configuration errors.

### Step 4: Preview Infrastructure Changes
- Execute `terraform plan` to review the Security Group configuration.

### Step 5: Apply the Configuration
- Run `terraform apply` to create the Security Group in AWS, securing the Attendance API.

---

## 🔚 Conclusion
This guide provides the steps to set up a Security Group for the Attendance API using Terraform, enabling secure, managed API access.

## 🔗 References

| **Reference**                         | **Link**                                                                                                      |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Terraform AWS Provider Documentation  | [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)                  |
| AWS Security Group Documentation      | [AWS Security Group Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) |

---

## 📞 Contact Information

| **Name**          | **Email**                                                |
|-------------------|----------------------------------------------------------|
| Amit Nagar        | [amit.nagar@mygurukulam.co](mailto:amit.nagar@mygurukulam.co) |

---



