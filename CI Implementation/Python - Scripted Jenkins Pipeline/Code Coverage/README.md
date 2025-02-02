
## Code Coverage - Scripted Jenkins Pipeline
---  
| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 10-10-24   | Version 1 | Komal Jaiswal   | 11-10-24       |                |                |                |

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
| **pytest**  | Latest    | Plugin for measuring code coverage in Python applications.      |

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
![image](https://github.com/user-attachments/assets/65d46cf8-8dbe-44e8-95f0-ebfad5b49866)
![image](https://github.com/user-attachments/assets/c84ff085-6af4-4b18-aaab-6cc6ab704910)


### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for code coverage under the Pipeline section → Provide the repository link, credentials, and file path.
![image](https://github.com/user-attachments/assets/54b89f13-05f0-4b73-9228-c29fab3f59b2)
![image](https://github.com/user-attachments/assets/11bd7e52-fad7-43b9-a942-8c3e5c6888e6)

### 6. 🖥️ Click on **Build** to initiate the pipeline.
![image](https://github.com/user-attachments/assets/249072ae-8311-4800-b234-3793341c6c42)

### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/5a9bf81e-f46b-4146-b5f6-c807fb6a7c3a)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/f3a516f6-b985-493f-a816-dbdeff12952d)
![image](https://github.com/user-attachments/assets/79d5a667-08cc-4585-ba05-599f21750eda)
![image](https://github.com/user-attachments/assets/be5af2a5-18e7-41d9-9eb0-6bc3eeda1219)


### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/823140fb-67e1-4b2c-abaf-d62499047b4b)

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

