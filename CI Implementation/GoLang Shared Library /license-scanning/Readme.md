# License Scanning for Shared Library 
---  

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 17-10-2024      | Version 2    | Amit Nagar         | 19-10-2024        |             |             |             |
---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🚀 Global Configurations](#-global-configurations)
4. [💥 Steps to Configuration for License Scanning](#-steps-to-configuration-for-license-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
License scanning is crucial for identifying the licenses of third-party libraries utilized by this shared library. By integrating license scanning into the CI/CD pipeline, we ensure compliance with licensing requirements, mitigating legal risks. This proactive approach is vital for maintaining the overall integrity of applications that depend on this library. Regular checks help in adhering to licensing obligations.

---

## ⚙️ Pre-requisites

| Dependency      | Version   | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| **Build Tool**   | Latest    | Required for building and managing project dependencies. |
| **License Scanning Tool** | Latest    | A tool to check for licenses and compliance of dependencies. |

---
## 🚀 Global Configuration
**Here we do global configuration for shared library, go to manage Jenkins.....> system......> Global Trusted Pipeline Libraries & provide the required details as you can see in images-**
![Screenshot 2024-10-14 150428](https://github.com/user-attachments/assets/f88f3a86-1823-4f72-ad64-0adfd641a988)
![Screenshot 2024-10-14 150516](https://github.com/user-attachments/assets/8fbb331d-41fd-4a9f-8eea-8838d370eab1)

---

## 💥 Steps to Configuration for License Scanning
### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License Scanning`).

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.


### 4. 🚀 Create the repository to add a vars file which will be used in the pipeline script.


### 5. 🚀 Choose Pipeline as the job type --> Add your pipeline script for License Scanning analysis in the pipeline script.


### 6. 🚀 Then Click on build to run the pipeline.


### 7. 🚀 Now we are able to see the build complete.


### 8. 🚀 Click on Console Output to see the complete build.


Jenkinsfile
```


```
---

## 📛 Conclusion
Integrating license scanning into our Jenkins pipeline is a crucial step in ensuring that our shared library complies with licensing requirements for third-party dependencies. This automated approach not only enhances legal compliance but also enables early detection of potential licensing issues during development. By proactively managing these risks, we can maintain a secure and trustworthy foundation for all applications utilizing this library. Continuous vigilance in license management ensures that our software remains compliant and resilient against legal challenges.

---
## 📞 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


---

## 📚 References

| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| https://spdx.dev/                                 | **SPDX - Software Package Data Exchange** |
| https://opensource.org/licenses                   | **Open Source Licenses** |
| https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/License-Scanning-POC|**Manual POC**|
