# AMI- Scripted Jenkins Pipeline  
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay  Bansal | 11-10-2024  | Version 1  | Vinay  Bansal     | 11-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Scripted pipelines for AMI](#-steps-to-conguration-scripted-pipelines-for-ami)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document outlines the process for creating an Amazon Machine Image (AMI) using Jenkins and Packer. An AMI serves as a template for launching new instances in AWS,
enabling efficient and consistent deployments. By automating the AMI creation process through Jenkins, users can streamline their CI/CD workflows, ensuring that new instances 
are built with the latest configurations and software. This guide will provide step-by-step instructions for setting up Jenkins and Packer to build and manage AMIs effectively.

---

## ⚙️ Pre-requisites

| Prerequisite              | Description                                                             |
|---------------------------|-------------------------------------------------------------------------|
| AWS Account               | An active AWS account to create and manage AMIs.                       |
| Jenkins                   | A Jenkins server installed and running to manage the CI/CD pipeline.    |
| Packer                    | Packer installed on the Jenkins server for creating AMIs.              |
| Git                       | Git installed to manage source code and configuration files.            |
| AWS CLI                   | AWS Command Line Interface (CLI) installed and configured with credentials. |
| IAM Permissions           | IAM role with permissions to create AMIs and launch instances.         |
| Ubuntu AMI                | An existing Ubuntu AMI ID for the source image in the Packer template.  |
| Jenkins Credentials       | AWS credentials set up in Jenkins for accessing AWS resources.          |


---

## 💥 Steps to Configuration Scripted pipelines for AMI

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `AMI`).

### 3. 🚀 Provide a description for the pipeline that performs AMI.


### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM

### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for AMI in the pipeline script for SCM ...> add repo link & credintial, file path.


### 6. 🚀 Then Click on build to run the pipeline to perform

### 7.🚀 Now we are able to see build complete-


### 8.🚀 Click on Console Output to see the complete build.


### 9.🚀 Review the stages of the build process in the console output.



---

## 📛 Conclusion
This document provided a detailed guide for creating Amazon Machine Images (AMIs) using Jenkins and Packer, streamlining the deployment process.
By automating AMI creation, teams can ensure consistency and efficiency in their cloud infrastructure. Implementing these practices enhances the overall CI/CD pipeline, enabling faster and more reliable application delivery.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@nanditasahu031/packer-create-nginx-ami-using-packer-f9cb600791a6| **Medium** |
|https://skeltonthatcher.com/2017/09/26/using-packer-create-windows-aws-amis-declarative-build-agents/| **Skelton Thatcher** |
