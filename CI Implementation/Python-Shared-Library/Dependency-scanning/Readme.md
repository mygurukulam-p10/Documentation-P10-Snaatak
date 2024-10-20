# Dependency Scanning for Python- Shared Library 
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by    |📅 Last edited on   |   ✍️L0 Reviewer   | ✍️ L1 Reviewer|✍️ L2 Reviewer|
|-------------|-------------|------------|-----------------|----------------|-------------------|-----------------|----------------|
| Megha Tyagi | 14-10-2024  | Version 1  | Megha Tyagi     | 20-10-2024     |     Aayush             |           Deepak      |   Anjali Kaushal|

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🚀 Global Configurations](-global-configuration)
4. [💥 Steps to Configuration Dependency Scanning](#-steps-to-conguration-dependency-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
Dependency scanning is essential for detecting security vulnerabilities in third-party libraries utilized by this shared library. By integrating dependency scanning into
the CI/CD pipeline, we ensure that only secure dependencies are employed, mitigating potential security risks. This proactive approach is critical for maintaining the
overall security of applications that rely on this library. Regular checks help keep our software safe and up to date.


---

## ⚙️ Pre-requisites

| Dependency      | Version   | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| **Python3**         | >= 3.6    | Required to run the Python virtual environment and install packages. |
| **pip**             | Latest    | Python package manager used to install and manage dependencies. |
| **venv**            | Built-in  | Python module for creating virtual environments.                |
| **safety**          | Latest    | A security tool to check for known vulnerabilities in dependencies. |

---
## 🚀 Global Configuration
**Here we do global configuration for shared library, go to manage jenkins.....> system......> Global Trusted Pipeline Libraries & provide the required details as you can see in images-**
![Screenshot 2024-10-14 150428](https://github.com/user-attachments/assets/f88f3a86-1823-4f72-ad64-0adfd641a988)
![Screenshot 2024-10-14 150516](https://github.com/user-attachments/assets/8fbb331d-41fd-4a9f-8eea-8838d370eab1)

---


## 💥 Steps to Configuration to Dependency Scanning
### 1. 🚀 Open your Jenkins Dashboard.
<img width="944" alt="Dashboard" src="https://github.com/user-attachments/assets/32ea261e-9e15-4dc4-9dfe-237965e974be">

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).

<img width="959" alt="image" src="https://github.com/user-attachments/assets/5526340f-4125-4979-992b-e9ec7dc546fb">


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
<img width="954" alt="image" src="https://github.com/user-attachments/assets/56dc24b9-4106-4e3b-afdc-32824aaf132e">


### 4. 🚀 Create the repo for add vars file which will be using in pipeline script.
![Screenshot 2024-10-14 091456](https://github.com/user-attachments/assets/5344b607-3b44-418c-91f9-7691c0bd2e69)
![Screenshot 2024-10-20 110530](https://github.com/user-attachments/assets/668b8997-d8e1-4cb5-af74-0df975b119b7)
![Screenshot 2024-10-20 110540](https://github.com/user-attachments/assets/5dec564e-f3fd-46ef-a7f3-52e56f7bd646)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Dependency Scanning analysis in the pipeline script.
![Screenshot 2024-10-20 110517](https://github.com/user-attachments/assets/8e27b451-92f2-48a4-be1b-fd9017938a8c)



### 6. 🚀 Then Click on build to run the pipeline to perform.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete.
![Screenshot 2024-10-20 110453](https://github.com/user-attachments/assets/46df56e0-60a1-40e0-8e26-cf2ab795ad56)



### 8.🚀 Click on Console Output to see the complete build.
![Screenshot 2024-10-20 110354](https://github.com/user-attachments/assets/79d85948-cd1c-4c89-9936-c7f4fdd90b16)
![Screenshot 2024-10-20 110406](https://github.com/user-attachments/assets/d2aaa190-48d8-4818-ab90-b1e1ab6b3946)
![Screenshot 2024-10-20 110426](https://github.com/user-attachments/assets/cfd41a91-e344-414f-b668-000b8faec083)




---

## 📛 Conclusion
Integrating dependency scanning into our Jenkins pipeline is a vital step in safeguarding our shared library against security vulnerabilities in third-party 
dependencies. This automated approach not only enhances software reliability but also enables early detection of potential security issues during development. 
By proactively addressing these risks, we can maintain a secure and trustworthy foundation for all applications utilizing this library. Continuous vigilance
in dependency management ensures that our software remains resilient against evolving security threats.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co|

---

## 📚 References

| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://pypi.org/project/pip-audit/| **Pip Audit** |
|https://safetycli.com/product/safety-cli?utm_source=data&utm_medium=redirect&utm_campaign=data_rd&utm_id=0624&utm_content=marketing| **Safety Docs** |
|https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency-Scanning-POC|**Manual POC**|

