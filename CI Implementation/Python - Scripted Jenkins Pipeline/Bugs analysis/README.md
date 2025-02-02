# Bug Analysis - Jenkins Pipeline with Bandit

---  
| Author          | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-----------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal Jaiswal   | 10-10-24   | Version 1 | Komal Jaiswal   | 11-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🧰 Setting Up Bandit for Bug Analysis](#-setting-up-bandit-for-bug-analysis)
   - [Jenkins Job Configuration](#jenkins-job-configuration)
4. [📈 Reviewing and Interpreting the Bandit Report](#-reviewing-and-interpreting-the-bandit-report)
5. [📌 Conclusion](#-conclusion)
6. [📞 Contact Information](#-contact-information)
7. [📖 References](#-references)

---

### 🔍 Overview
This guide provides a step-by-step approach to integrating **Bandit** within a Jenkins pipeline for bug analysis in the Attendance API microservice. Bandit inspects Python code for security vulnerabilities, enabling early detection and proactive resolution of issues. This integration contributes to robust software development practices by identifying risks in real-time.

---

## ⚡ Requirements

To successfully set up bug analysis using Bandit in Jenkins, ensure the following dependencies are met:

| Dependency      | Version       | Description                                                             |
|-----------------|---------------|-------------------------------------------------------------------------|
| **Python3**     | >= 3.6        | Required for running Bandit in a Python environment.                    |
| **pip**         | Latest        | Python's package manager, essential for managing dependencies.          |
| **Bandit**      | Latest        | Security analysis tool to identify vulnerabilities in Python code.      |

---

## 🧰 Setting Up Bandit for Bug Analysis

This section outlines the steps to configure a Jenkins job for bug analysis using Bandit, from job creation to pipeline configuration.

### Jenkins Job Configuration

1. **Navigate to Jenkins Dashboard:**  
   Start by logging into Jenkins and going to the main dashboard.
![image](https://github.com/user-attachments/assets/176a2a5f-b171-4fa2-b603-f87b998009da)
   
2. **Create a New Job:**  
   - Click on **New Item**.
![image](https://github.com/user-attachments/assets/96f8b16c-e851-4561-bbd4-a1af20fbf071)

   - Name the job (e.g., `Python-Bug-Analysis-Pipeline`) and select **Pipeline** as the job type.
![image](https://github.com/user-attachments/assets/b84103de-118b-4f19-89c6-ceb32f0b506b)

3. **Add Description:**  
   - Include a detailed job description.
![image](https://github.com/user-attachments/assets/d72262fd-cf4f-482c-b236-7dd26b74d6ca)


4. **Source Control Setup:**  
   - Link the job to your source control repository that contains the `Jenkinsfile` for pipeline configuration.
![image](https://github.com/user-attachments/assets/aa1a3e4b-dea6-472f-bc40-da4164db22f9)
![image](https://github.com/user-attachments/assets/50e86cb0-879d-4380-b0a3-4ae0ffffe2ce)


### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for dependency scanning under the Pipeline section → Provide the repository link, credentials, and file path.

![image](https://github.com/user-attachments/assets/7004a8a9-551d-4746-b992-bb6dacbb8579)
![image](https://github.com/user-attachments/assets/331c6d97-e9fb-46c9-8b1c-e8efa968ef31)


### 6. 🖥️ Click on **Build** to initiate the pipeline.
![image](https://github.com/user-attachments/assets/a952fa85-fd4e-452a-8e0e-2c43f4067c65)


### 7. 🖥️ Observe as the build completes.
[image](https://github.com/user-attachments/assets/2d3408ac-4494-43b8-89f0-38900cd8df42)


### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/de7733b5-3d28-48fc-8dc2-924a6b03669d)
![image](https://github.com/user-attachments/assets/4098f73e-f2a5-449c-915e-52410a302f0d)


### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/4098f73e-f2a5-449c-915e-52410a302f0d)


### 10. 🖥️ Chek the report of the scan 
![image](https://github.com/user-attachments/assets/f3e788fb-89bd-4a45-be49-a3765e348687)


#### Report

![image](https://github.com/user-attachments/assets/809da3de-434d-42d8-8e44-7212c2b3e573)
![image](https://github.com/user-attachments/assets/7b5977d5-a1e8-4bfb-a3cd-95a40a87058d)
![image](https://github.com/user-attachments/assets/ef86cdaa-aec7-4a5c-83c9-d1babb1c6c10)
![image](https://github.com/user-attachments/assets/280010f6-a128-4613-99ac-c9c24b2b59c1)



---

## 📈 Reviewing and Interpreting the Bandit Report

After the pipeline execution, a `txt` report generated by Bandit will be available as an artifact in Jenkins. The report provides insights into detected security issues, including:

- **Severity Level:** Each issue is categorized as LOW, MEDIUM, or HIGH, indicating the potential risk.
- **File and Line Number:** Shows the exact location of the issue in the codebase.
- **Issue Confidence:** Measures the confidence level of the finding (LOW, MEDIUM, HIGH).
- **Recommendation:** Provides guidance for resolving the identified security vulnerabilities.

---

## 📌 Conclusion

Integrating Bandit into a Jenkins pipeline enhances the security and reliability of the Attendance API microservice by continuously monitoring for vulnerabilities. This approach ensures that any security risks in the codebase are promptly identified and addressed, reinforcing safe development practices.

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
| [Bandit Documentation](https://bandit.readthedocs.io/en/latest/)                    | Comprehensive guide on using Bandit for security analysis. |
| [Python Security Analysis](https://pypi.org/project/bandit/)                        | Overview of Bandit's features and usage.              |
| [Jenkins CI Documentation](https://www.jenkins.io/doc/)                             | Documentation on configuring Jenkins CI pipelines.    |

