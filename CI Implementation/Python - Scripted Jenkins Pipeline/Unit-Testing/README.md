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
![image](https://github.com/user-attachments/assets/2f76c7dc-dac1-49d1-9370-22444094e988)
![image](https://github.com/user-attachments/assets/6de360dd-a3f6-4ce6-a83c-e4e7cec22e03)

### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for unit testing under the Pipeline section → Provide the repository link, credentials, and file path.

### 6. 🖥️ Click on **Build** to initiate the pipeline.

### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/4816f1b9-08d9-42f5-8828-b404a3f86f90)

### 8. 🖥️ Review the **Console Output** for build details.


### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/6086b7b6-74d2-4bf5-8ae8-6354a92e0160)

### 10. 🖥️ Check the report of the unit test analysis.
  ![image](https://github.com/user-attachments/assets/802aacbb-7dfe-4bbd-9b40-6fc10eec8491)


#### Report
![image](https://github.com/user-attachments/assets/74d8e637-3e03-48f2-8ad6-96e470c09d87)
![image](https://github.com/user-attachments/assets/7056af6f-7427-492d-9c36-75b7ce242548)

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
