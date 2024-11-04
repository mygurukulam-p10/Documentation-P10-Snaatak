# Attendance App Launch Template Setup (Development) - Terraform

| **Author**    | **Date**   | **Version** | **Reviewed By (L0)** | **Reviewed By (L1)** | **Reviewed By (L2)** |
|---------------|------------|-------------|-----------------------|-----------------------|-----------------------|
| Amit Nagar    | 05-11-24   | 1.0         | -                     | -                     | -                     |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features](#key-features)
4. [Benefits](#benefits)
5. [Steps for Launch Template Setup](#steps-for-launch-template-setup)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

### 🎯 Purpose
This document provides a comprehensive guide for setting up a Launch Template for the Attendance App in a development environment using Terraform, aimed at automating EC2 instance configurations.

### 📖 Introduction
The Launch Template setup is a critical part of the infrastructure configuration, enabling consistent and repeatable deployments of EC2 instances with predefined settings. This template simplifies the management of EC2 instances and integrates seamlessly with other AWS resources.

---

### 🔑 Key Features

| **Feature**                      | **Description**                                                |
|----------------------------------|---------------------------------------------------------------|
| **Automated Instance Creation**  | Facilitates quick launch of EC2 instances with specified settings. |
| **Version Control**              | Allows for versioning of templates to manage changes easily.  |
| **User Data Customization**      | Enables initialization scripts for instance configuration.    |
| **Integration with Auto Scaling**| Works with Auto Scaling groups to dynamically manage instances. |

---

### 🏆 Benefits

| **Benefit**          | **Description**                                                             |
|----------------------|-----------------------------------------------------------------------------|
| **Efficiency**       | Reduces time to deploy instances by using pre-defined templates.             |
| **Consistency**      | Ensures that all instances are created with the same configurations.        |
| **Flexibility**      | Easily update the Launch Template to modify instance parameters.            |
| **Enhanced Security** | Improved security through controlled access configurations and settings.    |

---

### 🛠 Steps for Launch Template Setup

#### Step 1: Format the Terraform Code
Use `terraform fmt` to format the code for consistency.

#### Step 2: Validate the Configuration
Run `terraform validate` to check for syntax errors in your Terraform configuration.

#### Step 3: Preview Infrastructure Changes
Execute `terraform plan` to review the proposed changes and ensure everything is set up correctly.

#### Step 4: Apply the Configuration
Run `terraform apply` to create the Launch Template in AWS, enabling efficient provisioning of EC2 instances.

---

### 🔚 Conclusion
This guide outlines the steps necessary for setting up a Launch Template for the Attendance App in a development environment using Terraform. By utilizing a Launch Template, you can ensure that EC2 instances are launched with consistent configurations, facilitating easier management and scaling.

---

### 🔗 References

| **Reference**                         | **Link**                                                                                                 |
|---------------------------------------|----------------------------------------------------------------------------------------------------------|
| Terraform AWS Provider Documentation  | [Terraform AWS Provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)              |
| AWS Launch Template Documentation     | [AWS Launch Template Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launch-templates.html) |
| Attendance App Infra Repo             | [Infrastructure Repository](https://github.com/mygurukulam-p10/infrastructure-repo)                      |

---

### 📞 Contact Information

| **Name**       | **Email**                                      |
|----------------|------------------------------------------------|
| Amit Nagar     | [amit.nagar@mygurukulam.co](mailto:amit.nagar@mygurukulam.co) |

---

