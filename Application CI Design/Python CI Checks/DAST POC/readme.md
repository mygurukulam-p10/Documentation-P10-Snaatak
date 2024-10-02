# Proof of Concept (POC) for DAST in Python
![image](https://github.com/user-attachments/assets/5d990352-2e84-4bed-b6d8-0a4f5c638055)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 01-10-24 | version 1 | Vinay Bansal | 02-10-24 |

## 🔍 Purpose
We are preparing this document so that we can easily provide a completed guide to step DAST which is designed in Python to manage attendance-api information.

  
## 📑 Table of Contents
- [📖Introduction](#introduction)
- [⚙️ Pre-Requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📧 Contact Information](#-contact-information )
- [📚 References](#-references )


## 📖Introduction 
In this document, I will show how to set up and run DAST using OWASP ZAP, an open-source security tool. This Proof of Concept (PoC) will demonstrate how DAST can help detect and fix security issues to make web application more secure before it's launched.


## ⚙️ Pre-Requisites
- Java
- OWASP ZAP

## 🖥 System Requirements

| Hardware Specifications | Minimum Requirement  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 2GB                    |
| Disk                     | 5GB                   |
| OS                       | Ubuntu(22.04)          |


## 🚀 Run-Time Dependency

| Name       | Version  | Description                                         |
|------------|----------|-----------------------------------------------------|
| Java       | 17.0.2   | Required for running Java applications and OWASP ZAP. |
| OWASP ZAP  | 2.15.0   | Open source web application security scanner.       |





## 🏗 Architecture

![image](https://github.com/user-attachments/assets/ae16e1ad-cf7a-457d-8fe5-68ac46930f95)

- The browser sends a request to the web application server.
- The request passes through the OWASP ZAP proxy, which can inspect and modify it.
- The server processes the request and sends a response back through the OWASP ZAP proxy.
- The proxy forwards the response to the browser.
- **This setup helps security testers identify vulnerabilities such as Cross-Site Scripting (XSS), SQL Injection, and other common web application security issues.**


## 📥 Step-by-step Installation
### Install git
```
sudo apt install git
```
###  Step 1: Clone the Git Repository
```
https://github.com/OT-MICROSERVICES/attendance-api.git
```
### Step 2: Change Directory
Change Directory to where your code is
```
cd attendance-api
```
### Step 3. Setup ZAP

* Visit zap [website](https://www.zaproxy.org/docs/) and check the different installation packages for different OS

* Run the following command to download zap linux package using `wget`, then to extract the package.

```
wget https://github.com/zaproxy/zaproxy/releases/download/v2.15.0/ZAP_2.15.0_Linux.tar.gz
```
![image](https://github.com/user-attachments/assets/ab3bebed-df72-4469-833b-10916807268d)

* Extract the tar.gz file
```
tar -xf ZAP_2.15.0_Linux.tar.gz
```
![image](https://github.com/user-attachments/assets/7aee1aec-cc9b-414c-a051-0e0b885b5c95)


### Step 4. Change Directory
Change Directory to where your Zap file is
```
cd ZAP_2.15.0
```

### Step 5. Run ZAP
* Now, to run our zap for analysis process.  Now running zap via zap.sh via -cmd or in daemon mode as it run the zap in Cli mode as shown below

```
<path to zap.sh> -port <port_no> -cmd -quickurl <url of website>
```

* <path to zap.sh> This is the executable file for OWASP ZAP
* The -port specifies the port on which ZAP will listen.
* -cmd indicates that the command should be executed in command-line mode.
* The -quickurl flag followed by the <url_of_website> parameter starts ZAP with the specified target URL.


### Step 5. Scanning API url

* The API and ZAP tool have been deployed on a virtual server. It has been ensured that the API is functioning correctly, and we can now proceed with the testing phase. For this process the following command was used:

```
 ./zap.sh -cmd -quickurl http://localhost:8080/apidocs -quickprogress -quickout ~/report.html
```
![image](https://github.com/user-attachments/assets/28f09b6c-9a16-46cc-8956-06bb138d4442)



### Step 6. Verify Reports 

* Navigate to the location where you saved your reports. Locate the generated `.html` reports. Ensure that vulnerabilities are correctly identified.

![image](https://github.com/user-attachments/assets/f334d786-477e-405f-8152-ca6ab55fa780)



The reports include information about the risk level and the number of alerts categorized. Following this overview, the reports provide specific details on each alert, presenting the alert name along with a concise description

Like we found Content **Security Policy Header is not set**. Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. 




##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |



## 📚 References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| OWASP documentation           | https://www.zaproxy.org/    |
|DAST Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Python%20CI%20Checks/DAST%20Doc/readme.md|
