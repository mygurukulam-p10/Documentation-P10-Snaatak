# Proof of Concept (POC): Cred Snanning - GitLeaks

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 22-09-2024         | 1.0       | Aayush Gaur  | POC: Credential Scanning               |
| 26-09-2024         | 1.1       | Aayush Gaur  | Updated Introduction & Flow Diagram               | 

### Table of Contents
- [Introduction](#introduction)
- [Flow Diagram](#flow-diagram)
- [Steps To Install gitleaks](#steps-to-install-gitleaks)
- [Perform Cred Scanning](#perform-cred-scanning)
- [Conclusion](#conclusion)
- [Best Practices](#best-practices)
- [Refrences](#refrences)

### Introduction
This POC is regarding performing cred scanning by using  gitleaks and step to perform cred scanning 

### ⚙️ Pre-requisites for Credential Scanning

- **Git**: For managing the repository where the scan will take place.
- **Gitleaks**: For performing the actual credential scanning.

### System Requirements for Credential Scanning
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                   |
| Disk                     | 5 GB free disk space   |
| OS                       | Ubuntu 22.04 LTS       |


### 🛠️ Build-Time Dependency for Credential Scanning

| 🛠️ Name  | 📦 Version | 📄 Description |
|----------|------------|----------------|
| **Gitleaks** | Latest     | Detects hardcoded secrets, passwords, and API keys in the codebase. |



### 🚀 Run-Time Dependency for Credential Scanning

| 🚀 Name  | 📦 Version       | 📄 Description                                    |
|---------|------------------|--------------------------------------------------|
| **Git**  | 2.+              | Required for repository management during scans. |
| **Gitleaks** | Latest         | Executes credential scanning on the repository.  |

### Flow Diagram
![Screenshot from 2024-09-27 20-30-32](https://github.com/user-attachments/assets/e60c796f-7372-43ad-852d-d89cc5e3c8b7)


### Steps To Install gitleaks

**Step 1**. Install

Gitleaks can be installed using package-manager, Docker, or Go. Gitleaks is also available in binary form for many popular platforms and OS types on the releases page ``` https://github.com/gitleaks/gitleaks/releases ```

![Screenshot from 2024-09-25 18-21-45](https://github.com/user-attachments/assets/b7ab3c68-9e6a-4109-afe3-a18607f8ca86)


**Step 2**. Download the latest version of Gitleaks

Copy the URL of latest version and paste it.
```
wget https://github.com/gitleaks/gitleaks/releases/download/v8.19.2/gitleaks_8.19.2_linux_x64.tar.gz
```
![Screenshot from 2024-09-25 18-20-51](https://github.com/user-attachments/assets/1cf6a017-83a6-4081-84e7-e8b088f03848)

**Step 3**: Extract the file by using below command
```
tar -zxvf gitleaks_8.19.2_linux_x64.tar.gz
```
![Screenshot from 2024-09-25 18-26-31](https://github.com/user-attachments/assets/6e8145fa-10c2-4c30-8d32-e3dd54027bc1)

**Step 4**: Copy gitleaks file to /usr/local/bin

After extracting the file, copy the file into this path
```
sudo cp gitleaks /usr/local/bin/
gitleaks version

```
![Screenshot from 2024-09-25 18-29-40](https://github.com/user-attachments/assets/c4c3acf9-b3a0-4335-a759-479bd50ddb31)

### Perform Cred Scanning

**Step 1.** Go to the repo in which have to perform scanning
```
cd <repo>
```

**Step 2** Now run this below command to scan 

Run this command it we show the result if any sensitive information detected
```
gitleaks detect -v
```
![Screenshot from 2024-09-25 18-41-40](https://github.com/user-attachments/assets/933dba1e-9b5b-4555-877e-0b9666e523c5)

### Conclusion
Credential scanning is an essential practice for maintaining the security and integrity of codebases. By implementing regular scans, Access Controls, Using Secrets Managers, organizations can significantly reduce the risk of exposing sensitive information. GitLeaks offer robust solutions for integrating credential scanning into CI pipelines, ensuring continuous protection against credential leaks.

## Contact Information 
|Name|Email Address|
|:---:|:---:|
|Aayush|aayush.gaur.snaatak@mygurukulam.co|

## References 
|links | Description |
|-------|-----------|
|https://github.com/gitleaks/gitleaks| GitLeaks Understanding |
|https://www.jit.io/resources/appsec-tools/the-developers-guide-to-using-gitleaks-to-detect-hardcoded-secrets| Cred Scanning |


