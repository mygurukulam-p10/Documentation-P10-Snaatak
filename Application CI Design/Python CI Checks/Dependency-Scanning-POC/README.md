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
 
<details>
  <summary>4. Run a scan</summary>

  <details>
    <summary> i. First scan</summary>

   Run the scan on `pyproject.toml`:

    ```
    safety check -r pyproject.toml 
    ```

   ![safety 1](https://github.com/user-attachments/assets/fc275cf2-b465-436c-8937-4e352c11ff64)

  </details>

  <details>
    <summary> ii. Second scan</summary>

   Now run the scan on `poetry.lock`:

    ```
    safety check -r poetry.lock
    ```

   ![Safety 2](https://github.com/user-attachments/assets/35d48844-08c2-40c6-9ace-de72a1ea1648)
   ![safety 3](https://github.com/user-attachments/assets/f8c1326e-fbac-4160-a2a8-be540196c119)
   ![safety 4](https://github.com/user-attachments/assets/8b5ba782-7aa2-4325-ad20-1e20d0584b4c)

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

