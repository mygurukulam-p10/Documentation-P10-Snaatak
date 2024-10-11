# Unit Testing - Scripted Jenkins Pipeline with Unittest

---

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 10-10-24   | Version 1 | Komal Jaiswal   | 10-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🛠️ Configuring Unit Tests](#-configuring-unit-tests)
4. [📌 Conclusion](#-conclusion)
5. [📞 Contact Information](#-contact-information)
6. [📖 References](#-references)

---

### 🔍 Overview
This document provides a comprehensive guide to setting up unit testing using **unittest** within a Jenkins pipeline specifically for the Attendance API microservice. **Unittest**, the built-in Python testing framework, supports structured and repeatable testing for every function, class, or module, ensuring that each component of the code behaves as expected. Integrating unit testing into Jenkins allows for continuous validation, supporting robust code quality management.

---

## ⚡ Requirements

### Dependencies

| Dependency      | Version   | Description                                                       |
|-----------------|-----------|-------------------------------------------------------------------|
| **Python3**     | >= 3.6    | Required for running the Python environment and unit tests.      |
| **pip**         | Latest    | Python package manager, for handling dependencies.               |
| **unittest**    | Built-in  | Built-in Python library for unit testing.                        |

---

## 🛠️ Configuring Unit Tests

### 1. 🖥️ Go to your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/c45dfc53-c999-443e-9ced-a7005897ceb7)

### 2. 🖥️ Click **New Item** → Enter a job name, such as `Python-Unittest-Pipeline`.
![image](https://github.com/user-attachments/assets/8e37a852-ab27-408a-99fc-3782c0171273)
![image](https://github.com/user-attachments/assets/6e464981-75ea-4a8f-acc9-e822ba1fb192)

### 3. 🖥️ Provide a detailed description of the pipeline's purpose and tasks.
![image](https://github.com/user-attachments/assets/ed83a840-a0e3-4d1f-bd85-45b693854e12)

### 4. 🖥️ Create a repository to add the `Jenkinsfile` that will contain the pipeline script.
![image](https://github.com/user-attachments/assets/2020bd6d-32ec-4a63-aa09-6d44bd8405f5)
![image](https://github.com/user-attachments/assets/43506432-7818-4166-95fb-8b8c52977ccd)


### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for unit testing under the Pipeline section → Provide the repository link, credentials, and file path.

![image](https://github.com/user-attachments/assets/f186bc32-017a-491d-a34e-c5a8d662f9c2)
![image](https://github.com/user-attachments/assets/664292c5-d3cd-4aaa-a30a-a453fb35b7df)


### 6. 🖥️ Click on **Build** to initiate the pipeline.
![image](https://github.com/user-attachments/assets/f436d184-85fb-4686-be77-5c3e4e98ee05)


### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/7d4ce80d-f664-4c8c-8fd2-72755637d5e2)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/14d5e015-a3b6-40bb-b259-c02038f3060b)

### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/c5eff9f2-9977-48b0-8438-b6598dfcaaf6)

### 10. 🖥️ Check the report of the unit test analysis.
![image](https://github.com/user-attachments/assets/e968047b-5580-4a55-b540-1e8231a67192)



#### Report
![image](https://github.com/user-attachments/assets/91782ce4-3f8a-4c8c-95f3-863870f61b23)

---

## 📌 Conclusion
Integrating unit testing with **unittest** into a Jenkins scripted pipeline ensures the Attendance API microservice’s core components function as expected, contributing to reliable and maintainable software development practices.

---

## 📞 Contact Information
For questions, feedback, or further assistance, reach out to:

| Name          | Email address                        |
|---------------|-------------------------------------|
| Komal Jaiswal | komal.jaiswal.snaatak@mygurukulam.co |

---

## 📖 References
| Links                                                                               | Descriptions                                          |
|-------------------------------------------------------------------------------------|-------------------------------------------------------|
| [Unittest Documentation](https://docs.python.org/3/library/unittest.html)          | Guide on using unittest for testing in Python.       |
| [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/)       | Documentation on creating Jenkins pipelines.         |
| [Unit Testing Best Practices](https://docs.python-guide.org/writing/tests/)       | Best practices for unit testing in Python.           |
