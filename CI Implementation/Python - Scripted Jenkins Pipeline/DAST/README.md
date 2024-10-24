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
![image](https://github.com/user-attachments/assets/2cc72c49-88f2-4989-a40c-85fa79496102)


### 5. 🖥️ Choose Pipeline as the job type → Add your pipeline script for DAST under the Pipeline section → Provide the repository link, credentials, and file path.
![image](https://github.com/user-attachments/assets/e910bb31-9dca-4705-a9bf-de081847bcc8)
![image](https://github.com/user-attachments/assets/7a2636f6-8ee7-4ce2-8826-1adff4e9c518)


### 6. 🖥️ Click on **Build** to initiate the pipeline.
![image](https://github.com/user-attachments/assets/d0eec085-3b44-467e-ab2f-0f0f353bb7a5)


### 7. 🖥️ Observe as the build completes.
![image](https://github.com/user-attachments/assets/52d13d5f-3193-4c5b-925e-0cfe9d0522ba)

### 8. 🖥️ Review the **Console Output** for build details.
![image](https://github.com/user-attachments/assets/b1524ae4-d55e-4a04-bb14-4c41a96c063c)


### 9. 🖥️ Check each stage in the console output for successful completion.
![image](https://github.com/user-attachments/assets/dd7504c9-8ce3-4a8f-b860-63442a0349ca)

### 10. 🖥️ Check the report of the security analysis.
![image](https://github.com/user-attachments/assets/d24cb137-656c-4e99-aa7e-35e19825fe31)


#### Report
![image](https://github.com/user-attachments/assets/cc18d77f-b269-4ce4-8ff7-adf93c65ff84)
![image](https://github.com/user-attachments/assets/dc02ef6d-ceb8-46e8-941d-e371e6beaa53)
![image](https://github.com/user-attachments/assets/de7d7386-405b-48ca-bb97-6ab3d91e2240)
![image](https://github.com/user-attachments/assets/f3af8233-9340-4e21-8cd9-692d0ddf9bb2)


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

