# Python CI Checks - Dependency Scanning - Proof of Concept 🚀

| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|----------------|----------------|
| Komal Jaiswal | 25-09-2024 | 1.0 | Komal Jaiswal  | 26-09-2024 |

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
3. [Step-by-step installation](#step-by-step-installation)
4. [References](#references)
5. [Contact Information](#contact-information)

## Purpose 🎯
This document aims to provide a comprehensive overview of dependency scanning in Python project like we have or ```Attendance-API``` , emphasizing its importance in Continuous Integration (CI) pipelines.


## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | single-core              |
| RAM                     | 1GB                    |
| Disk                    | 10GB                   |
| OS                      | Ubuntu 22.04           |

### Dependencies

| Name     | Version | Description                              |
|----------|---------|------------------------------------------|
| Python   | 3.10    | Programming language for the application |
| pip      | 22.0.2  | To manage python packages and it's dependencies|


### Note :- I am using safety as a Dependency Scanning tool in my POC.

## Step-by-step installation

Safety is a command-line tool that checks your installed dependencies for known security vulnerabilities. To demonstrate the capabilities of ```Safety```, here’s a simple setup guide. We will be using our Microservice ```Attendance-API```

1. **Clone the Repository**

```
https://github.com/OT-MICROSERVICES/attendance-api.git
```
### In this Repository you will see these files in which we will perform the dependency scanning.

![image](https://github.com/user-attachments/assets/732e63c8-d8d9-4aa7-afd3-ba304a1dea5f)
![image](https://github.com/user-attachments/assets/dd51547e-3445-44e4-81da-e09368ec99a1)


2. **Install Safety**:

```bash
pip install safety
```

3. **Go to Attendance-API**

```
cd attendance-api/
```
 
4. <details>

<summary>**Run a scan**</summary>

1. <details>

First Run the scan on ``` pyproject.toml``` 

```
safety check -r pyproject.toml 
```
![image](https://github.com/user-attachments/assets/54417b55-4943-46e8-aa1b-4c61967b62ff)

</details>

2. <details>
Now Run the scan on ```poetry.lock```

```
safety check -r poetry.lock
```

![image](https://github.com/user-attachments/assets/62fcc804-4260-4529-ac2e-02e69df57197)
![image](https://github.com/user-attachments/assets/dece325d-abbc-4a78-a744-f713666dca35)
![image](https://github.com/user-attachments/assets/e257b470-898c-4e19-b479-2a2714b21d20)

</details>

</details>


This configuration will run a safety check on every request, scanning the `pyproject.toml` and `poetry.lock` file for known vulnerabilities as in our ```ATTENDANCE-API``` , We are having these 2 files.


## 📚 References

| **Reference**                                                  | **Link**                                                                                          |
|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Safety Documentation**                                      | [Safety Docs](https://pyup.io/safety/)                                                           |
| **Snyk Python Documentation**                                 | [Snyk Docs](https://docs.snyk.io/products/snyk-open-source/language-and-package-manager-support/snyk-for-python) |
| **GitHub Dependency Scanning Documentation**                           | [Dependabot Docs](https://github.com/mygurukulam-p10/Documention/edit/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency%20Scanning/README.md)                          |
| **pip-audit Documentation**                                   | [pip-audit Docs](https://pypi.org/project/pip-audit/)                                          |
| **OWASP Dependency-Check**                                   | [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)                       |


## 📧 Contact Information

For more information on how to implement CI or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |

