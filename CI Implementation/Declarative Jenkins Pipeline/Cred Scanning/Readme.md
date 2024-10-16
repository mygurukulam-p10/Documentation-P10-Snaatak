# Credential Scanning- Declarative Jenkins Pipeline  <img width="41" alt="Screenshot 2024-10-03 165327" src="https://github.com/user-attachments/assets/53e0a6de-677f-410c-9050-e942a917e6a2">
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |  ✍️ L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 03-10-2024  | Version 1  | Megha Tyagi     | 07-10-2024     |     Ayush Yadav             |    Rishabh             |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Declarative pipelines for cred scanning](#-steps-to-conguration-declarative-pipelines-for-cred-scanning)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This guide outlines the steps to set up **GitLeaks** for scanning your Git repository for hardcoded secrets and credentials using a **Jenkins Declarative Pipeline**. This setup does not use Docker and assumes you have GitLeaks installed on your Jenkins server.

---

## ⚙️ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **GitLeaks**: For performing the actual credential scanning
3. **Go**: To ensure performance and concurrency
3. **Jenkins Credentials**: Add any required credentials (e.g., GitHub tokens) in Jenkins.
4. **Repo**: To apply cred scanning.
---

## 💥 Steps to Configuration Declarative pipelines for cred scanning

### 1. 🚀 Open your Jenkins Dashboard.
<img width="951" alt="Screenshot 2024-10-03 171617" src="https://github.com/user-attachments/assets/e6448943-be68-4a6f-91d1-76e29d206a2f">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `cred-scanning`).
![Screenshot 2024-10-03 171735](https://github.com/user-attachments/assets/898d9d35-3c76-4a15-8570-8eb5b5bbbbab)

### 3. 🚀 Provide a description for the pipeline that performs credential scanning.
<img width="947" alt="image" src="https://github.com/user-attachments/assets/df35108b-2228-48f0-86b5-bd310c3b9da7">

### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM
![Screenshot 2024-10-07 114436](https://github.com/user-attachments/assets/32ce93b8-47fc-4b06-aeaa-76a96fc5ba49)
<img width="920" alt="image" src="https://github.com/user-attachments/assets/61dd60c2-bacc-4820-ab39-a0c6fb0ddda1">


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for credential scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 114130](https://github.com/user-attachments/assets/6817dc45-4998-4f46-86c7-523d646af706)

### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/8e0b140e-3cb9-4b40-babd-75fb6963a653">

### 7.🚀 Now we are able to see build complete-
<img width="959" alt="build completed" src="https://github.com/user-attachments/assets/598eeb56-73b2-4d9f-a144-ac2f7d570091">

### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 114403](https://github.com/user-attachments/assets/e38f126d-3528-4814-ae4a-2d788046c353)
![Screenshot 2024-10-07 114349](https://github.com/user-attachments/assets/69ec0316-2b8e-4fb6-89a7-962214691a38)

### 9. 🚀 Once the report is generated, you will be able to see the HTML report.
![Screenshot 2024-10-07 120849](https://github.com/user-attachments/assets/0f86bc89-e2af-403b-9105-2e0467567e3f)

### 10.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 121001](https://github.com/user-attachments/assets/92ccc100-5bed-4f17-9579-c026e0d7f9ca)

---

## 📛 Conclusion
By following this guide, you have successfully configured GitLeaks for credential scanning in your Jenkins Declarative Pipeline. This setup ensures that your Git repository is continuously monitored for hardcoded secrets and sensitive data, helping you maintain the security and integrity of your codebase. Regularly scanning for credentials using automated tools like GitLeaks helps in identifying potential security risks early in the development process. Be sure to monitor the reports generated and integrate the scanning process into your CI/CD pipeline to catch vulnerabilities before code is deployed.

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
