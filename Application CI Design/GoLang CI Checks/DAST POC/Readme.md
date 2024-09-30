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
Dynamic Application Security Testing (DAST) is a security testing approach that analyzes web applications in their running state to identify vulnerabilities. By simulating real-world attacks, DAST tests for weaknesses that can be exploited by malicious actors. Unlike static analysis, which examines code without executing it, DAST evaluates applications in their live environment, providing insight into security issues that may only be apparent during runtime.



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

Like we found Content **Security Policy Header is not set **. Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.

***
## Conclusion

* In conclusion, ZAP to check the security of our Java application, and it helped us find and fix some problems. But, it's important to know that keeping the application secure is an ongoing task. The information we got from this test is like a good starting point to make the application even more secure. It is advised to treat these findings seriously and implement appropriate remediation measures for overall security of our application.

* Since, security risks are always changing, it's really important to keep paying attention and regularly test and fix any issues in our applications. This ongoing effort is key to making sure our application stays strong and secure.



## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


  ***
## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| OWASP documentation           | https://www.zaproxy.org/    |

