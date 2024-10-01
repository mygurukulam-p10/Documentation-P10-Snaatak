# Proof of Concept (POC) for DAST


| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 28-09-24    | version 1  | Amit Nagar      | 29-09-24       |

![image](https://github.com/user-attachments/assets/69e2000a-b7e2-428c-ad99-3dc29fdc9661)

## Table of Contents
- [Introduction](#introduction)
- [System Requirements](#system-requirements)
- [Runtime Dependency](#runtime-dependency)
- [OWASP ZAP](#owasp-zap)
- [Flow Diagram](#flow-diagram)
- [Proof of Concept (PoC)](#proof-of-concept-poc)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)


## Introduction 
In this document, I will show how to set up and run DAST using OWASP ZAP, an open-source security tool. This Proof of Concept (PoC) will demonstrate how DAST can help detect and fix security issues to make web application more secure before it's launched.



## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 10GB                   |
| OS                       | Ubuntu(22.04)          |


## Runtime Dependency

| Name       | Version  | Description                                         |
|------------|----------|-----------------------------------------------------|
| Java       | 17.0.2   | Required for running Java applications and OWASP ZAP. |
| OWASP ZAP  | 2.15.0   | Open source web application security scanner.       |




## OWASP ZAP
OWASP ZAP (Zed Attack Proxy) is an open-source security tool designed for testing the security of web applications. Developed by the Open Web Application Security Project (OWASP), ZAP is primarily used for performing Dynamic Application Security Testing (DAST). It helps identify vulnerabilities such as SQL Injection, Cross-Site Scripting (XSS), and other common security flaws by actively scanning and simulating attacks on running applications.


## Flow Diagram

![image](https://github.com/user-attachments/assets/ae16e1ad-cf7a-457d-8fe5-68ac46930f95)


## Proof of Concept (PoC)
### Pre-requisites

### 1. Setup ZAP

* Visit zap [website](https://www.zaproxy.org/docs/) and check the different installation packages for different OS

* Run the following command to download zap linux package using `wget`, then to extract the package.

```
wget https://github.com/zaproxy/zaproxy/releases/download/v2.15.0/ZAP_2.15.0_Linux.tar.gz
tar -xf ZAP_2.15.0_Linux.tar.gz
```

![Screenshot from 2024-09-28 01-47-20](https://github.com/user-attachments/assets/17b28002-9f4b-4813-b154-a103fd9748fa)


### 2. Run ZAP
* Now, to run our zap for analysis process.  Now running zap via zap.sh via -cmd or in daemon mode as it run the zap in Cli mode as shown below

```
<path to zap.sh> -port <port_no> -cmd -quickurl <url of website>
```

* <path to zap.sh> This is the executable file for OWASP ZAP
* The -port specifies the port on which ZAP will listen.
* -cmd indicates that the command should be executed in command-line mode.
* The -quickurl flag followed by the <url_of_website> parameter starts ZAP with the specified target URL.

### 3. Scanning API url

* The API and ZAP tool have been deployed on a virtual server. It has been ensured that the API is functioning correctly, and we can now proceed with the testing phase. For this process the following command was used:

*
```
 ./zap.sh -cmd -quickurl https://7e8b-103-55-60-194.ngrok-free.app -quickprogress -quickout ~/report.html
```
![Screenshot from 2024-09-29 01-59-52](https://github.com/user-attachments/assets/f069d110-9e9b-4791-ae70-a09ffac92994)



### 4. Verify Reports 

* Navigate to the location where you saved your reports. Locate the generated `.html` reports. Ensure that vulnerabilities are correctly identified.
![Screenshot from 2024-09-29 02-44-26](https://github.com/user-attachments/assets/a72d0f86-590c-4314-9d0a-c2c562d67264)




The reports include information about the risk level and the number of alerts categorized. Following this overview, the reports provide specific details on each alert, presenting the alert name along with a concise description

Like we found Content **Security Policy Header is not set **. Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. 

***
## Conclusion
In this Proof of Concept (PoC), OWASP ZAP was used to perform Dynamic Application Security Testing (DAST) on the emplpyee-api application. The testing revealed several security issues, including the absence of a Content Security Policy (CSP) header. CSP helps protect the application against Cross-Site Scripting (XSS) and data injection attacks by allowing developers to specify which sources of content are safe to load.



## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


  ***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| OWASP documentation           | https://www.zaproxy.org/    |

