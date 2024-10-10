# Dynamic Application Security Testing (DAST) - Scripted Jenkins Pipeline with OWASP ZAP

---  
| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 10-10-24   | Version 1 | Komal Jaiswal   | 10-10-24       |                |                |                |

---

## Table of Contents
1. [🔍 Overview](#-overview)
2. [⚡ Requirements](#-requirements)
3. [🛠️ Configuring DAST](#-configuring-dast)
4. [📌 Conclusion](#-conclusion)
5. [📞 Contact Information](#-contact-information)
6. [📖 References](#-references)

---

### 🔍 Overview
This README provides a comprehensive guide to setting up Dynamic Application Security Testing (DAST) within a Jenkins pipeline specifically for the Attendance API microservice. Utilizing **OWASP ZAP**, this process helps identify security vulnerabilities in running applications, ensuring a more secure software delivery lifecycle. By integrating DAST checks into the CI/CD pipeline, the system continuously monitors security, enabling proactive measures to address potential threats.

---

## ⚡ Requirements

### Dependencies

| Dependency        | Version   | Description                                                     |
|-------------------|-----------|-----------------------------------------------------------------|
| **Java**          | >= 8     | Required for running OWASP ZAP.                                |
| **OWASP ZAP**     | Latest    | Open-source tool for finding vulnerabilities in web applications. |

---

## 🛠️ Configuring DAST

### 1. 🖥️ Go to your Jenkins Dashboard.
![image](https://github.com/user-attachments/assets/c45dfc53-c999-443e-9ced-a7005897ceb7)

### 2. 🖥️ Click **New Item** → Enter a job name, such as `OWASP-ZAP-DAST-Pipeline`.
![image](https://github.com/user-attachments/assets/8e37a852-ab27-408a-99fc-3782c0171273)
![image](https://github.com/user-attachments/assets/5666213b-8935-406f-8843-bb390ec4ed94)

### 3. 🖥️ Provide a detailed description of the pipeline's purpose and tasks.
![image](https://github.com/user-attachments/assets/f758e119-0c51-4f2d-90d6-6c21321d2195)

### 4. 🖥️ Create a repository to add the `Jenkinsfile` that will contain the pipeline script.
![image](https://github.com/user-attachments/assets/636e7e85-40bb-40ae-90a3-035b1030d951)

### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for DAST under the Pipeline section → Provide the repository link, credentials, and file path.

### 6. 🖥️ Click on **Build** to initiate the pipeline.

### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/64906f37-7281-4c33-b7a1-24b1e5c882ce)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/bce9013b-b3ab-4798-834f-5e42744e09cb)

### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/29c12bb5-95e2-404d-9a70-21fa942ec17a)

### 10. 🖥️ Check the report of the security analysis.
![image](https://github.com/user-attachments/assets/e4db0490-d2c0-49a8-a7d8-ea2ef79e347b)

#### Report
![image](https://github.com/user-attachments/assets/74d8e637-3e03-48f2-8ad6-96e470c09d87)
![image](https://github.com/user-attachments/assets/7056af6f-7427-492d-9c36-75b7ce242548)

---

## 📌 Conclusion
Integrating DAST analysis into a Jenkins scripted pipeline enhances the security of the Attendance API microservice by identifying vulnerabilities before deployment. This approach facilitates proactive security measures, ensuring a robust software delivery lifecycle.

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
| [OWASP ZAP Documentation](https://www.zaproxy.org/docs/)                           | Comprehensive guide on using OWASP ZAP for DAST.    |
| [Jenkins Pipeline Documentation](https://www.jenkins.io/doc/book/pipeline/)       | Documentation on creating Jenkins pipelines.         |
| [OWASP Top Ten](https://owasp.org/www-project-top-ten/)                            | Overview of the top ten security vulnerabilities.     |

