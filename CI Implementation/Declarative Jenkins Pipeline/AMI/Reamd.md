# AMI- Declarative Jenkins Pipeline  
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 11-10-2024  | Version 1  | Megha Tyagi     | 11-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Declarative pipelines for AMI](#-steps-to-conguration-declarative-pipelines-for-ami)
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

## 💥 Steps to Configuration Declarative pipelines for AMI

### 1. 🚀 Open your Jenkins Dashboard.
<img width="951" alt="Screenshot 2024-10-03 171617" src="https://github.com/user-attachments/assets/e6448943-be68-4a6f-91d1-76e29d206a2f">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `AMI`).
![Screenshot 2024-10-11 133443](https://github.com/user-attachments/assets/0c239f01-f2da-4197-bc01-4b4a967ed716)

### 3. 🚀 Provide a description for the pipeline that performs AMI.
![Screenshot 2024-10-11 133505](https://github.com/user-attachments/assets/3ea7d3a0-5244-4550-bd07-c24ec91bf796)


### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM
![Screenshot 2024-10-11 134913](https://github.com/user-attachments/assets/b385b211-e7fe-46ea-b4b8-2b00ce9d1c92)
![Screenshot 2024-10-11 134928](https://github.com/user-attachments/assets/311f85a7-027a-4128-9522-5ea3e63a3dcf)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for AMI in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-11 133638](https://github.com/user-attachments/assets/be15b60c-00fc-43d0-88f0-f8e5502df2dd)
![Screenshot 2024-10-11 133651](https://github.com/user-attachments/assets/fee753a8-964a-4e39-abbf-a4423087c130)
![Screenshot 2024-10-11 134928](https://github.com/user-attachments/assets/c4b1aba6-ccd6-4bf2-8b58-d34175be55ad)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
![Screenshot 2024-10-11 133734](https://github.com/user-attachments/assets/b00a0ecb-0ce5-4482-aea4-3e8680df9787)


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-11 133747](https://github.com/user-attachments/assets/6fa9270c-e44c-416a-94a5-a745a7a7ff63)
![Screenshot 2024-10-11 133759](https://github.com/user-attachments/assets/b9ce3261-1275-4181-aa09-d51c88b1d43d)
![Screenshot 2024-10-11 133959](https://github.com/user-attachments/assets/c2921074-5839-44a8-bcd5-344f488d7aa0)
![Screenshot 2024-10-11 133828](https://github.com/user-attachments/assets/c5553f60-3096-4d84-a273-edd9209a6584)


### 9.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-11 133940](https://github.com/user-attachments/assets/8c5b1c81-56fa-4bdf-b813-a3d461594717)



---

## 📛 Conclusion
This document provided a detailed guide for creating Amazon Machine Images (AMIs) using Jenkins and Packer, streamlining the deployment process.
By automating AMI creation, teams can ensure consistency and efficiency in their cloud infrastructure. Implementing these practices enhances the overall CI/CD pipeline, enabling faster and more reliable application delivery.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---
## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://medium.com/@nanditasahu031/packer-create-nginx-ami-using-packer-f9cb600791a6| **Medium** |
|https://skeltonthatcher.com/2017/09/26/using-packer-create-windows-aws-amis-declarative-build-agents/| **Skelton Thatcher** |

