# License Scanning- Declarative Jenkins Pipeline  ![pluginIcon](https://github.com/user-attachments/assets/99182f40-0f7a-47bb-b1d0-2e014689d2dd)



---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 03-10-2024  | Version 1  | Megha Tyagi     | 03-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for License scanning](#-steps-to-conguration-declarative-pipelines-for-license-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines the process for setting up **Trivy** to perform license scanning on your project. Trivy is a versatile open-source vulnerability and security scanner, which can also be used to check for open source license compliance in your project's dependencies. By integrating Trivy into your pipeline, you can ensure that the licenses of third-party dependencies are properly managed, helping to avoid legal and compliance issues.

---

## ⚙️ Pre-requisites
1. **Trivy Installation**: Trivy, for performing the license scanning.
2. **Jenkins**: If you are integrating license scanning in a pipeline, ensure you have a CI/CD tool like Jenkins set up.
3. **Git**: Your project repository should be accessible via Git, and Git should be installed on the system where Trivy will run.
---
## 🔍 System Requirements
| Component         | Minimum Requirement       | Recommended Requirement     |
|-------------------|---------------------------|-----------------------------|
| **Processor**     | Dual-core CPU             | Quad-core CPU or higher     |
| **Memory**        | 2 GB RAM                  | 4 GB RAM or more            |
| **Disk Space**    | 500 MB                    | 1 GB or more                |
| **Operating System** | Linux, macOS, or Windows | Linux or macOS for best compatibility |

---

## 💥 Steps to Configuration Declarative pipelines for License scanning

### 1. 🚀 Open your Jenkins Dashboard.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/Dashboard.png

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License-scanning`).
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/click%20iten.png

### 3. 🚀 Provide a description for the pipeline that performs License scanning.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/description.png

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for License scanning in the pipeline configuration...>Click on Save to store the configuration.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/script.png

### 5. 🚀 Then Click on build to run the pipeline to perform
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/build.png

### 6.🚀 Now we are able to see build complete-
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/build%20status.png

### 7.🚀 Click on Console Output to see the complete build.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/console%20output-1.png
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/console%20output-2.png
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/console%20output-3.png

### 8. 🚀 Once the report is generated, you will be able to see the JSON report.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/Json%20Report.png

### 9.🚀 Review the stages of the build process in the console output.
https://github.com/mygurukulam-p10/Documention/blob/main/CI%20Implementation/Declarative%20Jenkins%20Pipeline/License%20Scanning/build%20stage.png

---

## 📛 Conclusion

By following this guide, you have successfully configured Trivy for license scanning, ensuring that all third-party dependencies in your project comply with the appropriate licenses. Regular license scanning helps mitigate legal risks and ensures adherence to open-source license policies. Integrating Trivy into your CI/CD pipeline allows for continuous monitoring of license compliance, giving you peace of mind and maintaining the integrity of your software development process.

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
|https://tinyurl.com/2nue65t2| **Medium** |
|https://aquasecurity.github.io/trivy/v0.17.2/| **Trivy** |
|https://dev.to/aws-builders/improving-your-cicd-pipeline-helm-charts-security-scanning-with-trivy-and-github-actions-3315|**Dev**|

