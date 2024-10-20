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
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `License Scanning`).
<img width="959" alt="image" src="https://github.com/user-attachments/assets/5526340f-4125-4979-992b-e9ec7dc546fb">

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
<img width="954" alt="image" src="https://github.com/user-attachments/assets/56dc24b9-4106-4e3b-afdc-32824aaf132e">

### 4. 🚀 Create the repository to add a vars file which will be used in the pipeline script.
![Screenshot 2024-10-14 091456](https://github.com/user-attachments/assets/5344b607-3b44-418c-91f9-7691c0bd2e69)
![Screenshot 2024-10-20 110530](https://github.com/user-attachments/assets/668b8997-d8e1-4cb5-af74-0df975b119b7)
![Screenshot 2024-10-20 110540](https://github.com/user-attachments/assets/5dec564e-f3fd-46ef-a7f3-52e56f7bd646)

### 5. 🚀 Choose Pipeline as the job type --> Add your pipeline script for License Scanning analysis in the pipeline script.
![Screenshot 2024-10-20 110517](https://github.com/user-attachments/assets/8e27b451-92f2-48a4-be1b-fd9017938a8c)

### 6. 🚀 Then Click on build to run the pipeline.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">

### 7. 🚀 Now we are able to see the build complete.
![Screenshot 2024-10-20 110453](https://github.com/user-attachments/assets/46df56e0-60a1-40e0-8e26-cf2ab795ad56)

### 8. 🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-20 110354](https://github.com/user-attachments/assets/79d85948-cd1c-4c89-9936-cf4fdd90b16)
![Screenshot 2024-10-20 110406](https://github.com/user-attachments/assets/d2aaa190-48d8-4818-ab90-b1e1ab6b3946)
![Screenshot 2024-10-20 110426](https://github.com/user-attachments/assets/cfd41a91-e344-414f-b668-000b8faec083)

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
