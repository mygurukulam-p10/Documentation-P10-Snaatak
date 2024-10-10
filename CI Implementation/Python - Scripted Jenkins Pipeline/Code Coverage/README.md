# Code Coverage - Scripted Jenkins Pipeline with Pytest

---  
| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 10-10-24   | Version 1 | Komal Jaiswal   | 10-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🛠️ Configuring Code Coverage](#-configuring-code-coverage)
4. [📌 Conclusion](#-conclusion)
5. [📞 Contact Information](#-contact-information)
6. [📖 References](#-references)

---

### 🔍 Overview
This README provides a comprehensive guide to setting up code coverage analysis within a Jenkins pipeline specifically for the Attendance API microservice. Utilizing **pytest** along with coverage tools, this process assesses the extent to which the codebase is tested, helping to ensure robust software quality. By integrating code coverage checks into the CI/CD pipeline, the system continuously monitors code quality, ensuring reliable and well-tested software for the Attendance API microservice.

---

## ⚡ Requirements

### Dependencies

| Dependency      | Version   | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| **Python3**     | >= 3.6    | Required for the Python environment and package installations.  |
| **pip**         | Latest    | The Python package manager, needed for handling dependencies.   |
| **pytest**      | Latest    | Framework for testing Python code.                              |
| **pytest-cov**  | Latest    | Plugin for measuring code coverage in Python applications.      |

---

## 🛠️ Configuring Code Coverage

### 1. 🖥️ Go to your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/c45dfc53-c999-443e-9ced-a7005897ceb7)

### 2. 🖥️ Click **New Item** → Enter a job name, such as `Python-Code-Coverage-Scripted-pipeline`.
![image](https://github.com/user-attachments/assets/8e37a852-ab27-408a-99fc-3782c0171273)
![image](https://github.com/user-attachments/assets/440c1f2e-dba3-4c55-a26e-42bef0864da9)

### 3. 🖥️ Provide a detailed description of the pipeline's purpose and tasks.
![image](https://github.com/user-attachments/assets/48247d1c-75cc-4e6d-b6f2-925da04615bc)

### 4. 🖥️ Create a repository to add the `Jenkinsfile` that will contain the pipeline script.
![image](https://github.com/user-attachments/assets/636e7e85-40bb-40ae-90a3-035b1030d951)

### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for code coverage under the Pipeline section → Provide the repository link, credentials, and file path.

### 6. 🖥️ Click on **Build** to initiate the pipeline.

### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/64906f37-7281-4c33-b7a1-24b1e5c882ce)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/bce9013b-b3ab-4798-834f-5e42744e09cb)

### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/29c12bb5-95e2-404d-9a70-21fa942ec17a)

### 10. 🖥️ Check the report of the coverage analysis.
![image](https://github.com/user-attachments/assets/e4db0490-d2c0-49a8-a7d8-ea2ef79e347b)

#### Report
![image](https://github.com/user-attachments/assets/74d8e637-3e03-48f2-8ad6-96e470c09d87)
![image](https://github.com/user-attachments/assets/7056af6f-7427-492d-9c36-75b7ce242548)



---

## 📌 Conclusion
Integrating code coverage analysis into a Jenkins scripted pipeline enhances the quality of the Attendance API microservice by ensuring thorough testing of the codebase. This approach allows for early detection of untested code paths, contributing to reliable and maintainable software development practices.

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
| [Pytest Documentation](https://docs.pytest.org/en/stable/)                        | Comprehensive guide on using pytest for testing.     |
| [pytest-cov Documentation](https://pytest-cov.readthedocs.io/en/latest/)          | Documentation on the pytest-cov plugin for coverage analysis. |
| [Manual POC](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Code-Coverage-POC) | Proof of Concept for Code Coverage                    |

