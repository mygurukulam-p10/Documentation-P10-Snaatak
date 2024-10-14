# Dependency Scanning for Python- Shared Library 
---  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 14-10-2024  | Version 1  | Megha Tyagi     | 14-10-2024     |

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
![Screenshot 2024-10-12 023632](https://github.com/user-attachments/assets/5a97a7ed-e04d-4124-a715-281bc3df7e80)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Uploading Screenshot 2024-10-12 023632.png…]()


### 4. 🚀 Create the repo for add vars file which will be using in pipeline script.
![Screenshot 2024-10-14 091456](https://github.com/user-attachments/assets/5344b607-3b44-418c-91f9-7691c0bd2e69)
![Screenshot 2024-10-15 022206](https://github.com/user-attachments/assets/875576cb-813b-40ce-83b1-3d183c37cc35)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Dependency Scanning analysis in the pipeline script.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/170e3879-7b80-4111-84c0-799afe5a4edc">


### 6. 🚀 Then Click on build to run the pipeline to perform.
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete.
<img width="950" alt="image" src="https://github.com/user-attachments/assets/6ead960b-7b8c-4378-a24d-8fe0ad95478c">


### 8.🚀 Click on Console Output to see the complete build.
<img width="943" alt="image" src="https://github.com/user-attachments/assets/b453f920-3e47-472d-add5-161b40c009e6">
<img width="934" alt="image" src="https://github.com/user-attachments/assets/bedd0bfa-d580-4c2b-b329-161e6d072c54">
<img width="944" alt="image" src="https://github.com/user-attachments/assets/8d622ab1-50a5-49ed-9b72-f79d249feb59">


### 9.🚀 Review the stages of the build process in the console output.
<img width="951" alt="image" src="https://github.com/user-attachments/assets/4cc09d7b-adee-45ec-aacf-8668a390257b">

---

## 📛 Conclusion
Integrating dependency scanning into our Jenkins declarative pipeline is a vital step in safeguarding our shared library against security vulnerabilities in third-party 
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

