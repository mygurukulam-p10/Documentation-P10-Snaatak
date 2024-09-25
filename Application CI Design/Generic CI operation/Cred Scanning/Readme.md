# Generic CI Operation: Credential Scanning
| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 22-09-2024         | 0.1       | Aayush Gaur  | Credential Scanning               |

### Purpose 

The purpose of this document is to provide a detailed explanation of **credential scanning** as part of a **Continuous Integration (CI) operation**. It explains what credential scanning is, why it is essential, the tools available for credential scanning, and how to implement it in CI pipelines. The document will also guide on best practices and offer a proof of concept (POC) for practical implementation. This ensures that sensitive data, such as passwords, API keys, and tokens, are not accidentally exposed in code repositories.

### Table of Contents
- [Introduction](#introduction)
- [What is Credential Scanning?](#what-is-credential-scanning)
- [Why Credential Scanning?](#why-credential-scanning)
- [Tools for Credential Scanning](#tools-for-credential-scanning)
- [Comparison of Credential Scanning Tools](#comparison-of-credential-scanning-tools)
- [Advantages of Credential Scanning](#advantages-of-credential-scanning)
- [Proof of Concept (POC)](#proof-of-concept-poc)
- [Best Practices](#best-practices)

### Introduction
Credential scanning is a process used in Continuous Integration (CI) to automatically check code for sensitive information like passwords, API keys, or tokens. It helps ensure that no critical data is accidentally shared in the codebase or in public repositories, which could lead to security issues.

As part of the CI pipeline, where code is built and tested automatically, credential scanning ensures that sensitive information doesn’t slip through unnoticed. This process is especially important in modern, fast-paced development environments where mistakes can happen.

### What is Credential Scanning?
Credential scanning is simply the act of scanning through your code, configuration files, or logs to check for sensitive information, like:

- **Passwords**
- **API keys**
- **Tokens (used to access services securely)**

If any of these are found in the code, they could be a security risk because attackers could steal and misuse them. Credential scanners identify patterns that match sensitive data, helping you catch and fix these issues early.

### Why Credential Scanning?

- **Prevents Leaks**: Sensitive information like API keys and passwords can be misused by attackers if exposed in code repositories. Scanning helps prevent such data leaks.
- **Automated Protection**: CI systems run multiple code checks quickly. Credential scanning ensures that no sensitive information is accidentally included in the build.
- **Compliance**: Some industries (healthcare, finance) require companies to keep sensitive data secure. Scanning helps organizations meet these standards.
- **Security Best Practice**: It’s a good practice to keep all credentials safe and out of your code. Regular scanning makes sure this happens.

 ### Tools for Credential Scanning

| Tool          | Features                                                                 | 
|---------------|--------------------------------------------------------------------------|
| **GitGuardian** | Monitors repositories in real-time to detect hardcoded secrets and sends alerts when something is found. |
| **TruffleHog**  | Looks for sensitive data by scanning for high-entropy strings, which might represent passwords or keys.
| **Gitleaks**    | Scans Git repositories for sensitive information in the code history.   | 
| **AWS Macie**   | Specifically for AWS environments, it scans your storage (like S3 buckets) for sensitive data. | 
| **SpectralOps** | Focuses on identifying secrets in code and configuration files and integrates well with CI pipelines. | 

### Comparison of Credential Scanning Tools

| Tool          | Features                                        | Strengths                            | Weaknesses                   |
|---------------|-------------------------------------------------|--------------------------------------|------------------------------|
| **GitGuardian** | Real-time monitoring and alerts                 | Catches issues immediately           | Expensive for larger teams    |
| **TruffleHog**  | Scans for high-entropy strings (like API keys)  | Works with many data types           | Can produce false positives   |
| **Gitleaks**    | Simple command-line tool                        | Lightweight and easy to use          | Lacks detailed dashboards     |
| **AWS Macie**   | Finds sensitive data in AWS storage             | Works best with AWS                  | Only works in AWS             |
| **SpectralOps** | Customizable with APIs                          | Works well with large projects       | Hard to set up for small teams |

### Advantages of Credential Scanning

| Advantage            | Description                                                                                          |
|----------------------|------------------------------------------------------------------------------------------------------|
| **Better Security**   | By catching credentials early, you prevent security breaches later on.                               |
| **Fast and Automatic**| The scanning is done automatically, meaning developers don’t need to check manually every time.      |
| **Meet Standards**    | Many industries require businesses to secure data properly, and credential scanning helps with this.  |
| **Avoid Data Leaks**  | By removing sensitive data before code is published, you avoid exposing it to hackers.               |

### Proof of Concept (POC)

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

### Steps To Install gitleaks

**Step 1**. Install

Gitleaks can be installed using Homebrew, Docker, or Go. Gitleaks is also available in binary form for many popular platforms and OS types on the releases page ``` https://github.com/gitleaks/gitleaks/releases ```

![Screenshot from 2024-09-25 18-21-45](https://github.com/user-attachments/assets/b7ab3c68-9e6a-4109-afe3-a18607f8ca86)


**Step 2**. Download the latest version of Gitleaks
```
wget https://github.com/gitleaks/gitleaks/releases/download/v8.19.2/gitleaks_8.19.2_linux_x64.tar.gz
```
![Screenshot from 2024-09-25 18-20-51](https://github.com/user-attachments/assets/1cf6a017-83a6-4081-84e7-e8b088f03848)

**Step 3**: Extract
```
tar -zxvf gitleaks_8.19.2_linux_x64.tar.gz
```
![Screenshot from 2024-09-25 18-26-31](https://github.com/user-attachments/assets/6e8145fa-10c2-4c30-8d32-e3dd54027bc1)

**Step 4**: Copy gitleaks file to /usr/local/bin
```
sudo cp gitleaks /usr/local/bin/
gitleaks version

```
![Screenshot from 2024-09-25 18-29-40](https://github.com/user-attachments/assets/c4c3acf9-b3a0-4335-a759-479bd50ddb31)


### Best Practices

| Best Practice           | Description                                                                                      |
|-------------------------|--------------------------------------------------------------------------------------------------|
| **Scan Early**           | Add scanning during development (before code is committed) to catch issues early.                |
| **Scan Regularly**       | Regularly scan the entire repository, as old commits may still contain sensitive data.           |
| **Access Controls**   | Implement strict access controls to limit who can view and modify sensitive information.             |
| **Handle False Positives**| Review flagged data carefully, as scanners can sometimes incorrectly flag harmless information.  |
| **Use Secrets Managers** | Store secrets (keys, passwords) in secure vaults like AWS Secrets Manager or HashiCorp Vault.     |


### Conclusion
Credential scanning is an essential practice for maintaining the security and integrity of codebases. By implementing regular scans, Access Controls, Using Secrets Managers, organizations can significantly reduce the risk of exposing sensitive information. Tools like GitLeaks, TruffleHog, GitGuardian, and SpectralOps offer robust solutions for integrating credential scanning into CI pipelines, ensuring continuous protection against credential leaks.

https://github.com/gitleaks/gitleaks
