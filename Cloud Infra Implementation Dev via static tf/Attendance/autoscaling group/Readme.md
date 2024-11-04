# Attendance App Infrastructure Setup (Development) - Terraform

| **Author**    | **Date**   | **Version** | **Reviewed By (L0)** | **Reviewed By (L1)** | **Reviewed By (L2)** |
|---------------|------------|-------------|-----------------------|-----------------------|-----------------------|
| Amit Nagar    | 05-11-24   | 1.0         | -                     | -                     | -                     |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features](#key-features)
4. [Benefits](#benefits)
5. [Steps for Infrastructure Setup](#steps-for-infrastructure-setup)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

### 🎯 Purpose
This document provides a step-by-step guide for setting up the infrastructure for the Attendance App in a development environment using Terraform. The setup includes configuring a Target Group for managing network traffic to the Attendance API.

### 📖 Introduction
The infrastructure for the Attendance App is set up within a Virtual Private Cloud (VPC) and includes resources like Security Groups and Target Groups to ensure a secure and scalable environment. The Target Group configuration is essential for load balancing and managing API traffic efficiently.

---

### 🔑 Key Features

| **Feature**                  | **Description**                                                                       |
|------------------------------|---------------------------------------------------------------------------------------|
| **Target Group Integration** | Configures a Target Group to manage traffic to the Attendance API.                    |
| **Custom VPC Configuration** | Sets up VPC and subnet for isolation and secure resource access.                     |
| **Security Group Controls**  | Controls inbound and outbound access for the application resources.                  |
| **Environment-Specific**     | Tailored for a development environment with reusable Terraform modules.              |

---

### 🏆 Benefits

| **Benefit**    | **Description**                                                              |
|----------------|------------------------------------------------------------------------------|
| **Scalability**| Allows easy scaling of the infrastructure to support app growth.             |
| **Security**   | Provides isolated networking with security groups and VPC setup.            |
| **Flexibility**| Terraform code can be adjusted to adapt to new environments easily.         |
| **Cost-Effective** | Tailored to development needs, minimizing excess resource usage.        |

---

### 🛠 Steps for Infrastructure Setup

#### Step 1: Initialize the Terraform Directory
- Run `terraform init` to set up the working directory and download required providers.

#### Step 2: Configure Variables
- Define values for VPC ID, Target Group settings, and other parameters in the `variables.tf` file.

#### Step 3: Format the Terraform Code
- Use `terraform fmt` to ensure the code is clean and consistently formatted.

#### Step 4: Validate the Configuration
- Run `terraform validate` to check for any syntax errors or issues with the configuration.

#### Step 5: Preview Infrastructure Changes
- Execute `terraform plan` to see a summary of resources that will be created.

#### Step 6: Apply the Configuration
- Run `terraform apply` to deploy the infrastructure, including VPC, Security Groups, and Target Group.

---

### 🔚 Conclusion
This setup document details the process of creating a development environment for the Attendance App, focusing on infrastructure configuration and Target Group setup using Terraform. This approach ensures a scalable and secure foundation for the Attendance API.

---

### 🔗 References

| **Reference**                         | **Link**                                                                                                 |
|---------------------------------------|----------------------------------------------------------------------------------------------------------|
| Terraform AWS Provider Documentation  | [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)              |
| AWS Target Group Documentation        | [AWS Target Group Documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/target-groups.html) |
| Attendance App Infra Repo             | [Infrastructure Repository](https://github.com/mygurukulam-p10/infrastructure-repo)                      |

---

### 📞 Contact Information

| **Name**       | **Email**                                      |
|----------------|------------------------------------------------|
| Amit Nagar     | [amit.nagar@mygurukulam.co](mailto:amit.nagar@mygurukulam.co) |

---

