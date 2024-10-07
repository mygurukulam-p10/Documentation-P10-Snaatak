# License Scanning- Declarative Jenkins Pipeline  ![pluginIcon](https://github.com/user-attachments/assets/99182f40-0f7a-47bb-b1d0-2e014689d2dd)

---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 03-10-2024  | Version 1.2  | Megha Tyagi     | 07-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [💥 Steps to Configuration Declarative pipelines for License scanning](#-steps-to-conguration-declarative-pipelines-for-license-scanning)
4. [📛 Conclusion](#-conclusion)
5. [📧 Contact Information](#-contact-information)
6. [📚 References](#-references)

---
### 💥 Introduction
This document outlines the process of implementing license scanning in your project using a declarative Jenkins pipeline,by integrating Trivy.The provided pipeline automates the scanning process, archives the results, and notifies the team via email upon completion. This approach enhances code quality and adherence to open-source licensing standards.

---

## ⚙️ Pre-requisites
1. **Trivy**: Trivy, for performing the license scanning.
2. **Jenkins**: If you are integrating license scanning in a pipeline, ensure you have a CI/CD tool like Jenkins set up.
3. **Git**: Your project repository should be accessible via Git, and Git should be installed on the system where Trivy will run.
---

## 💥 Steps to Configuration Declarative pipelines for License scanning

### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License-scanning`).
<img width="947" alt="click iten" src="https://github.com/user-attachments/assets/5bf27cc4-0246-437d-9b50-7c3c3c57f1c9">


### 3. 🚀 Provide a description for the pipeline that performs License scanning.
<img width="959" alt="description" src="https://github.com/user-attachments/assets/88d12b31-909e-4c70-98cd-683d8c67c8dd">

### 4. Create the repo for add jenkinfile which will be using in pipeline script for SCM.
![Screenshot 2024-10-07 125808](https://github.com/user-attachments/assets/6459a3dd-758e-4ba4-b613-39b789c7a8b1)
![Screenshot 2024-10-07 125038](https://github.com/user-attachments/assets/deb44112-f8b6-4733-a476-6909b97f8118)


### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for License scanning in the pipeline script for SCM ...> add repo link & credintial, file path.
![Screenshot 2024-10-07 124914](https://github.com/user-attachments/assets/fb01dd8a-a280-4a28-89e4-ec923ded631d)


### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
<img width="950" alt="image" src="https://github.com/user-attachments/assets/abcdc72d-8e8a-4680-b077-7c30bfdc3936">


### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-07 125004](https://github.com/user-attachments/assets/eaebff54-463a-4216-8470-7432e221e137)
![Screenshot 2024-10-07 125016](https://github.com/user-attachments/assets/6efc0b45-a52a-40e1-bc8c-c2f0b513201c)



### 9. 🚀 Once the report is generated, you will be able to see the JSON report.
![Screenshot 2024-10-07 124540](https://github.com/user-attachments/assets/e892dbcc-b027-40ea-b085-52a22479c477)



### 10.🚀 Review the stages of the build process in the console output.
![Screenshot 2024-10-07 125256](https://github.com/user-attachments/assets/c6820ed7-c0bc-4b61-8141-8f01522b62ab)

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

