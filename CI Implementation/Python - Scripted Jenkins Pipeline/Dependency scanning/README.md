# Dependency Scanning - Scripted Jenkins Pipeline

---  
| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 09-10-24   | Version 1 | Komal Jaiswal   | 09-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🛠️ Configuring Dependency Scanning](#-configuring-dependency-scanning)
4. [📌 Summary](#-summary)
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

### 1. 🖥️ Open your Jenkins Dashboard.

### 2. 🖥️ Click **New Item** → Enter a job name, such as `Dependency Scanning`.

### 3. 🖥️ Provide a detailed description of the pipeline's purpose and tasks.

### 4. 🖥️ Create a repository to add the `Jenkinsfile` that will contain the pipeline script.

### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for dependency scanning under the Pipeline section → Provide the repository link, credentials, and file path.

### 6. 🖥️ Click on **Build** to initiate the pipeline.

### 7. 🖥️ Observe as the build completes.

### 8. 🖥️ Review the **Console Output** for build details.

### 9. 🖥️ Check each stage in the console output for successful completion.

---

## 📌 Conclusion
Incorporating dependency scanning into a Jenkins scripted pipeline enhances the security of third-party libraries used in a project. This proactive step allows early identification of vulnerabilities, contributing to robust and reliable software development practices, especially for the Attendance API microservice.

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
