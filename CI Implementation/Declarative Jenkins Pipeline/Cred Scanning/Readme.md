# Credential Scanning- Declarative Jenkins Pipeline  <img width="41" alt="Screenshot 2024-10-03 165327" src="https://github.com/user-attachments/assets/53e0a6de-677f-410c-9050-e942a917e6a2">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 03-10-2024  | Version 1  | Megha Tyagi     | 03-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for cred scanning](#-steps-to-conguration-declarative-pipelines-for-cred-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This guide outlines the steps to set up **GitLeaks** for scanning your Git repository for hardcoded secrets and credentials using a **Jenkins Declarative Pipeline**. This setup does not use Docker and assumes you have GitLeaks installed on your Jenkins server.

---

## ⚙️ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **GitLeaks**: For performing the actual credential scanning
3. **Jenkins Credentials**: Add any required credentials (e.g., GitHub tokens) in Jenkins.
---
## 🔍 System Requirements
| Component         | Minimum Requirement       | Recommended Requirement     |
|-------------------|---------------------------|-----------------------------|
| **Processor**     | Dual-core CPU             | Quad-core CPU or higher     |
| **Memory**        | 4 GB RAM                  | 8 GB RAM or more            |
| **Disk Space**    | 1 GB                      | 10 GB or more (for larger repositories) |

---

## 💥 Steps to Configuration Declarative pipelines for cred scanning

### 1. 🚀 Open your Jenkins Dashboard.
<img width="951" alt="Screenshot 2024-10-03 171617" src="https://github.com/user-attachments/assets/e6448943-be68-4a6f-91d1-76e29d206a2f">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `cred-scanning`).
![Screenshot 2024-10-03 171735](https://github.com/user-attachments/assets/898d9d35-3c76-4a15-8570-8eb5b5bbbbab)

### 3. 🚀 Provide a description for the pipeline that performs credential scanning.
<img width="947" alt="image" src="https://github.com/user-attachments/assets/df35108b-2228-48f0-86b5-bd310c3b9da7">

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline configuration...>Click on Save to store the configuration.
<img width="956" alt="image" src="https://github.com/user-attachments/assets/3c946e0b-3656-47fe-80dd-cd67427662fe">

### 5. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 6.🚀 Now we are able to see build complete-
<img width="959" alt="build completed" src="https://github.com/user-attachments/assets/598eeb56-73b2-4d9f-a144-ac2f7d570091">

### 7.🚀 Click Build Now to run the pipeline and perform the credential scan.
<img width="959" alt="console 1" src="https://github.com/user-attachments/assets/6f7e4f8e-360f-4459-9564-12622bdf65e8">
<img width="929" alt="console 2" src="https://github.com/user-attachments/assets/5bce25f8-31ae-4e52-90b1-4016690e6424">
<img width="941" alt="console 3" src="https://github.com/user-attachments/assets/4b507ffe-c08b-4e41-804b-6f9bba05786e">

### 8. 🚀 Once the report is generated, you will be able to see the JSON report.
<img width="571" alt="json report" src="https://github.com/user-attachments/assets/b1b41e7b-bd0c-4fae-84a1-0c7acf64cc7b">

### 9.🚀 Review the stages of the build process in the console output.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/a5045da9-237a-45a6-8bcf-bda1138c9642">
---

## 📛 Conclusion

By following this guide, you have successfully configured GitLeaks for credential scanning in your Jenkins Declarative Pipeline without using Docker. This setup ensures that your Git repository is continuously monitored for hardcoded secrets and sensitive data, helping you maintain the security and integrity of your codebase. 
Regularly scanning for credentials using automated tools like GitLeaks helps in identifying potential security risks early in the development process. Be sure to monitor the reports generated and integrate the scanning process into your CI/CD pipeline to catch vulnerabilities before code is deployed.

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
|https://github.com/gitleaks/gitleaks| **GitLeaks Understanding** |
|https://www.jit.io/resources/appsec-tools/the-developers-guide-to-using-gitleaks-to-detect-hardcoded-secrets| **Cred Scanning** |
|https://tinyurl.com/2tbfm9w3|(POC): **Cred Snanning**|
