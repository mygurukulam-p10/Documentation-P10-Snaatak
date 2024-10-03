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
1. **Trivy**: Trivy, for performing the license scanning.
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
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License-scanning`).
<img width="947" alt="click iten" src="https://github.com/user-attachments/assets/5bf27cc4-0246-437d-9b50-7c3c3c57f1c9">


### 3. 🚀 Provide a description for the pipeline that performs License scanning.
<img width="959" alt="description" src="https://github.com/user-attachments/assets/88d12b31-909e-4c70-98cd-683d8c67c8dd">


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for License scanning in the pipeline configuration...>Click on Save to store the configuration.
<img width="932" alt="script" src="https://github.com/user-attachments/assets/35484b01-080e-4b53-b114-cb17cc530da9">


### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 6.🚀 Now we are able to see build complete-
<img width="944" alt="build status" src="https://github.com/user-attachments/assets/49018077-c6d0-4932-95a7-2234104acf87">


### 7.🚀 Click on Console Output to see the complete build.
<img width="959" alt="console output-1" src="https://github.com/user-attachments/assets/043588ff-d61c-47ba-a012-6448486dbbbd">
<img width="944" alt="console output-2" src="https://github.com/user-attachments/assets/db195395-d0d6-4101-af10-302296070893">
<img width="941" alt="console output-3" src="https://github.com/user-attachments/assets/764fdb1b-0193-4312-8f07-14371e008f4f">

### 8. 🚀 Once the report is generated, you will be able to see the JSON report.
<img width="702" alt="Json Report" src="https://github.com/user-attachments/assets/5f504303-a041-4193-9c99-1b209626bb77">


### 9.🚀 Review the stages of the build process in the console output.
<img width="951" alt="build stage" src="https://github.com/user-attachments/assets/829ace03-ceee-4f03-9a3a-cecc6a641635">


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

