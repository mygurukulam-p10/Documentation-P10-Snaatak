# License Scanning- Scripted Jenkins Pipeline  ![pluginIcon](https://github.com/user-attachments/assets/99182f40-0f7a-47bb-b1d0-2e014689d2dd)



---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 06-10-2024  | Version 1  | Vinay Bansal     | 10-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Scripted pipelines for License Scanning](#-steps-to-configuration-scripted-pipelines-for-license-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines the process for setting up **Trivy** to perform license scanning on your project. Trivy is a versatile open-source vulnerability and security scanner, which can also be used to check for open source license compliance in your project's dependencies. By integrating Trivy into your pipeline, you can ensure that the licenses of third-party dependencies are properly managed, helping to avoid legal and compliance issues.

---

## ⚙ Pre-requisites
1. **Trivy**: Trivy, for performing the license scanning.
2. **Jenkins**: If you are integrating license scanning in a pipeline, ensure you have a CI/CD tool like Jenkins set up.
3. **Git**: Your project repository should be accessible via Git, and Git should be installed on the system where Trivy will run.
---
## 🔍 System Requirements
| Component         | Minimum Requirement       | 
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 500 MB                    |
| **Operating System** | Linux, macOS, or Windows | 

![image](https://github.com/user-attachments/assets/eb91843f-c210-491f-8ba6-6ed7a61a4961)


## 💥 Steps to Configuration Scripted pipelines for License Scanning

### 1. 🚀 Open your Jenkins Dashboard.
![10](https://github.com/user-attachments/assets/11ac0745-d068-436d-9f97-6a6d356be797)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License-scanning`).
![2](https://github.com/user-attachments/assets/82f7c0e1-b0f6-47eb-98d9-5e39b2b2a4dc)


### 3. 🚀 Provide a description for the pipeline that performs License scanning.
![3](https://github.com/user-attachments/assets/b4ed058b-d2d8-4bab-90ad-8da333f6ec66)


### 4. Create the repo for add jenkinsfile which will be using in pipeline script for SCM.
![image](https://github.com/user-attachments/assets/8920b51a-80fc-40ca-b662-aa698fdfc7a1)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for License scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/19f80128-a236-4b3b-b55a-20f76c7ef643)


### 6.🚀 Now we are able to see build complete-
![6](https://github.com/user-attachments/assets/f35b295f-f940-417a-b04f-55e0fed689be)


### 7.🚀 Click on Console Output to see the complete build.
![7](https://github.com/user-attachments/assets/041e932f-31d4-480d-a9fd-ac2495bedcee)
![8](https://github.com/user-attachments/assets/893d45c0-aa1e-4a82-aa84-1b340d4d2da7)

### 8. 🚀 Once the report is generated, you will be able to see the JSON report.
![image](https://github.com/user-attachments/assets/5380a416-e52b-4455-939f-34f360231023)


### 9.🚀 Review the stages of the build process in the console output.
![9](https://github.com/user-attachments/assets/d8583d81-5970-4df8-97d4-865745b3ebe4)


---

## 📛 Conclusion

By following this guide, you have successfully configured Trivy for license scanning, ensuring that all third-party dependencies in your project comply with the appropriate licenses. Regular license scanning helps mitigate legal risks and ensures adherence to open-source license policies. Integrating Trivy into your CI/CD pipeline allows for continuous monitoring of license compliance, giving you peace of mind and maintaining the integrity of your software development process.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |


## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://aquasecurity.github.io/trivy/v0.18.3/installation/| **Installation** |
|https://vijetareigns.medium.com/securing-container-image-using-trivy-in-cicd-pipeline-fe445e18fb9a|Trivy in CICD Pipeline|
