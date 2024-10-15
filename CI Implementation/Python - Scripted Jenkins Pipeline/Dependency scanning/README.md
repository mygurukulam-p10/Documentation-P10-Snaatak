![image](https://github.com/user-attachments/assets/5b7f3b57-8600-476b-abd7-612566449a47)


# Dependency Scanning - Scripted Jenkins Pipeline

---  
| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 09-10-24   | Version 1 | Komal Jaiswal   | 11-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🛠️ Configuring Dependency Scanning](#-configuring-dependency-scanning)
4. [📌 Conclusion](#-conclusion)
5. [📞 Contact Information](#-contact-information)
6. [📖 References](#-references)

---

### 🔍 Overview
This README provides a comprehensive guide to setting up dependency scanning within a Jenkins pipeline specifically for the Attendance API microservice. This scanning process identifies potential security vulnerabilities in third-party libraries, helping to maintain secure and resilient software. By embedding this step into the CI/CD pipeline, the system automatically monitors for dependency risks, ensuring reliable updates and security for the Attendance API microservice.

---

## ⚡ Requirements

### Dependencies

| Dependency      | Version   | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| **Python3**     | >= 3.6    | Required for the Python environment and package installations.  |
| **pip**         | Latest    | The Python package manager, needed for handling dependencies.   |
| **venv**        | Built-in  | Python’s virtual environment module.                            |
| **safety**      | Latest    | Security tool for identifying vulnerabilities in dependencies.  |

---

## 🛠️ Configuring Dependency Scanning

### 1. 🖥️ Go to your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/f8013644-3ae2-4f6f-9c2d-c67f94650f62)

### 2. 🖥️ Click **New Item** → Enter a job name, such as `Python-Dependency-Scanning-Scripted-pipeline`.
![image](https://github.com/user-attachments/assets/66dc78e0-2460-4330-8758-ca2a70d04c6b)

### 3. 🖥️ Provide a detailed description of the pipeline's purpose and tasks.
![image](https://github.com/user-attachments/assets/619bbc9f-4e8f-4a88-bbfb-ddd01c874a3b)

### 4. 🖥️ Create a repository to add the `Jenkinsfile` that will contain the pipeline script.
![image](https://github.com/user-attachments/assets/66958772-e1ff-402b-bb0d-d9ae7282622c)
![image](https://github.com/user-attachments/assets/236301aa-7a67-4fb8-ae70-4d8d0acff2fe)

### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for dependency scanning under the Pipeline section → Provide the repository link, credentials, and file path.
![image](https://github.com/user-attachments/assets/ebb21928-5b36-4801-962d-c5fd961b9868)
![image](https://github.com/user-attachments/assets/f9263c52-c63b-4f47-9601-f4c7e79e5492)


### 6. 🖥️ Click on **Build** to initiate the pipeline.
![image](https://github.com/user-attachments/assets/5377695f-a505-4fb4-b6df-9e0aac650190)

### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/0acefc56-0a6e-41e0-a3a1-3e255c9b598e)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/c0e18b7c-fb74-40df-8497-b820279f70a6)

### 9. 🖥️ Check each stage in the console output for successful completion.

![image](https://github.com/user-attachments/assets/eb64f276-1c15-47fa-a591-ff150c604030)

### 10. 🖥️ Chek the report of the scan 
![image](https://github.com/user-attachments/assets/24d9ce3a-d70f-403f-a16d-a690c5079109)

#### Report

![image](https://github.com/user-attachments/assets/749c6574-d622-49f8-8c10-24b32d34a26e)
![image](https://github.com/user-attachments/assets/c1e767f3-4b34-4411-94f7-8ef7798ec450)
![image](https://github.com/user-attachments/assets/bf1b4b04-cd00-45f2-9f47-129eb5308c01)

---

## 📌 Conclusion
When we are using dependency scanning into a Jenkins scripted pipeline it enhances the security of third-party libraries used in our project. This step allows early identification of vulnerabilities, contributing to robust and reliable software development practices, especially for the Attendance API microservice as we are using that.

## 📞 Contact Information
For questions, feedback, or further assistance, reach out to:

| Name          | Email address                        |
|---------------|-------------------------------------|
| Komal Jaiswal | komal.jaiswal.snaatak@mygurukulam.co |

---

## 📖 References
| Links                                                                               | Descriptions                                          |
|-------------------------------------------------------------------------------------|-------------------------------------------------------|
| [Pip Audit](https://pypi.org/project/pip-audit/)                                    | Auditing tool for Python dependencies.                |
| [Safety CLI Documentation](https://safetycli.com/product/safety-cli)                | Documentation on the Safety CLI for dependency checks.|
| [Manual POC](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency-Scanning-POC) | Proof of Concept for Dependency Scanning              |
