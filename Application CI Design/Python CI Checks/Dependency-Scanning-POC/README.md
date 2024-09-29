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

---

2. **Install Safety**:

```bash
pip install safety
```
---

3. **Go to Attendance-API**

```
cd attendance-api/
```

---

4. **Run a Scan**

a.  First Scan on ```pyproject.toml```

```
safety check -r pyproject.toml 
```

 ![safety 1](https://github.com/user-attachments/assets/fc275cf2-b465-436c-8937-4e352c11ff64)
 
b. Second Scan on ```poetry.lock```

```
 safety check -r poetry.lock
```
   ![Safety 2](https://github.com/user-attachments/assets/35d48844-08c2-40c6-9ace-de72a1ea1648)
   ![safety 3](https://github.com/user-attachments/assets/f8c1326e-fbac-4160-a2a8-be540196c119)
   ![safety 4](https://github.com/user-attachments/assets/8b5ba782-7aa2-4325-ad20-1e20d0584b4c)




<details>
  <summary> Detailed Output Report of Above Scans </summary>


  <details>
    <summary> i. Output of First scan</summary>

 ```  +======================================================================================================================================+

 REPORT 

  Safety v3.2.7 is scanning for Vulnerabilities...
  Scanning dependencies in your files:

  -> pyproject.toml

  Using open-source vulnerability database
  No packages found
  Timestamp 2024-09-29 05:26:09
  0 vulnerabilities reported
  0 vulnerabilities ignored
+======================================================================================================================================+

 No known security vulnerabilities reported. 
```


  </details>

  <details>
    <summary> ii. Output of Second scan</summary>

   ```
+======================================================================================================================================+

 REPORT 

  Safety v3.2.7 is scanning for Vulnerabilities...
  Scanning dependencies in your files:

  -> poetry.lock

  Using open-source vulnerability database
  Found and scanned 34 packages
  Timestamp 2024-09-29 05:28:59
  8 vulnerabilities reported
  0 vulnerabilities ignored

+======================================================================================================================================+
 VULNERABILITIES REPORTED 
+======================================================================================================================================+

-> Vulnerability found in werkzeug version 2.3.6
   Vulnerability ID: 71595
   Affected spec: <=2.3.7
   ADVISORY: Werkzeug is a comprehensive WSGI web application library. If an upload of a file that starts with CR or LF and
   then is followed by megabytes of data without these characters: all of these bytes are appended chunk by chunk into internal...
   CVE-2023-46136
   For more information about this vulnerability, visit https://data.safetycli.com/v/71595/97c
   To ignore this vulnerability, use PyUp vulnerability id 71595 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in werkzeug version 2.3.6
   Vulnerability ID: 71594
   Affected spec: <3.0.3
   ADVISORY: Werkzeug is a comprehensive WSGI web application library. The debugger in affected versions of Werkzeug can
   allow an attacker to execute code on a developer's machine under some circumstances. This requires the attacker to get the...
   CVE-2024-34069
   For more information about this vulnerability, visit https://data.safetycli.com/v/71594/97c
   To ignore this vulnerability, use PyUp vulnerability id 71594 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in werkzeug version 2.3.6
   Vulnerability ID: 62019
   Affected spec: <2.3.8
   ADVISORY: Werkzeug 3.0.1 and 2.3.8 include a security fix: Slow multipart parsing for large parts potentially enabling DoS
   attacks.https://github.com/pallets/werkzeug/commit/b1916c0c083e0be1c9d887ee2f3d696922bfc5c1
   PVE-2023-62019
   For more information about this vulnerability, visit https://data.safetycli.com/v/62019/97c
   To ignore this vulnerability, use PyUp vulnerability id 62019 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in peewee version 3.16.2
   Vulnerability ID: 64952
   Affected spec: <3.17.1
   ADVISORY: Peewee 3.17.1 introduces enhancements to address a race condition issue by implementing stricter locking
   mechanisms around pool connection management.https://github.com/coleifer/peewee/commit/ea3fb11a9c2a4b0cd958a453dd287e408477eda5
   PVE-2024-64952
   For more information about this vulnerability, visit https://data.safetycli.com/v/64952/97c
   To ignore this vulnerability, use PyUp vulnerability id 64952 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in jinja2 version 3.1.2
   Vulnerability ID: 70612
   Affected spec: >=0
   ADVISORY: In Jinja2, the from_string function is prone to Server Side Template Injection (SSTI) where it takes the source
   parameter as a template object, renders it, and then returns it. The attacker can exploit it with INJECTION COMMANDS in a URI....
   CVE-2019-8341
   For more information about this vulnerability, visit https://data.safetycli.com/v/70612/97c
   To ignore this vulnerability, use PyUp vulnerability id 70612 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in jinja2 version 3.1.2
   Vulnerability ID: 64227
   Affected spec: <3.1.3
   ADVISORY: Jinja2 before 3.1.3 is affected by a Cross-Site Scripting vulnerability. Special placeholders in the template
   allow writing code similar to Python syntax. It is possible to inject arbitrary HTML attributes into the rendered HTML...
   CVE-2024-22195
   For more information about this vulnerability, visit https://data.safetycli.com/v/64227/97c
   To ignore this vulnerability, use PyUp vulnerability id 64227 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in jinja2 version 3.1.2
   Vulnerability ID: 71591
   Affected spec: <3.1.4
   ADVISORY: Jinja is an extensible templating engine. The `xmlattr` filter in affected versions of Jinja accepts keys
   containing non-attribute characters. XML/HTML attributes cannot contain spaces, `/`, `>`, or `=`, as each would then be...
   CVE-2024-34064
   For more information about this vulnerability, visit https://data.safetycli.com/v/71591/97c
   To ignore this vulnerability, use PyUp vulnerability id 71591 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


-> Vulnerability found in flask-caching version 2.0.2
   Vulnerability ID: 40459
   Affected spec: <=2.3.0
   ADVISORY: Flask-caching is vulnerable to CVE-2021-33026: Flask-Caching extension for Flask relies on Pickle for
   deserialization, which may lead to remote code execution or local privilege escalation. If an attacker gains access to cache...
   CVE-2021-33026
   For more information about this vulnerability, visit https://data.safetycli.com/v/40459/97c
   To ignore this vulnerability, use PyUp vulnerability id 40459 in safety’s ignore command-line argument or add the ignore to your
   safety policy file.


+======================================================================================================================================+
   REMEDIATIONS

  8 vulnerabilities were reported in 4 packages. For detailed remediation & fix recommendations, upgrade to a commercial license. 

+======================================================================================================================================+

 Scan was completed. 8 vulnerabilities were reported. 

+======================================================================================================================================+
```


  </details>

</details>


| Column             | Description                                                                        |
|--------------------|------------------------------------------------------------------------------------|
| Vulnerability ID    | The identifier for the vulnerability.                                             |
| Affected Spec       | The version range that is affected.                                              |
| Advisory            | A brief description of the advisory concerning the vulnerability.                 |
| CVE ID             | The CVE (Common Vulnerabilities and Exposures) identifier.                       |
| Additional Info     | Links for more information about the vulnerability.                              |


This configuration will run a safety check on every request, scanning the `pyproject.toml` and `poetry.lock` file for known vulnerabilities as in our ```ATTENDANCE-API``` , We are having these 2 files.


## 📚 References

| **Reference**                                                  | **Link**                                                                                          |
|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Safety Documentation**                                      | [Safety Docs](https://pyup.io/safety/)                                                           |
| **Snyk Python Documentation**                                 | [Snyk Docs](https://docs.snyk.io/products/snyk-open-source/language-and-package-manager-support/snyk-for-python) |
| **Dependency Scanning Documentation**                           | [Dependency scanning Doc](https://github.com/mygurukulam-p10/Documention/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency%20Scanning)                          |
| **pip-audit Documentation**                                   | [pip-audit Docs](https://pypi.org/project/pip-audit/)                                          |
| **OWASP Dependency-Check**                                   | [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)                       |


## 📧 Contact Information

For more information on how to implement CI or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |

