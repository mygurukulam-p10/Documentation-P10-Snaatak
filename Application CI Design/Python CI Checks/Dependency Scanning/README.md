
# 🐍 Python CI Checks: 🔍 Dependency Scanning - Documentation

![image](https://github.com/user-attachments/assets/1da54ff0-a4e1-4910-8c19-d1ffdbe4f1b3)

| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|----------------|----------------|
| Komal Jaiswal | 25-09-2024 | 1.0 | Komal Jaiswal  | 26-09-2024 |

## 📚 Table of Contents
- [Purpose](#purpose)
- [Introduction](#introduction)
- [What is Dependency Scanning?](#what-is-dependency-scanning)
- [Why Perform Dependency Scanning?](#why-perform-dependency-scanning)
- [Different Tools for Python Dependency Scanning and Comparison](#different-tools-for-python-dependency-scanning-and-comparison)
- [Advantages Dependency Scanning](#advantages-and-disadvantages-of-dependency-scanning)
- [Disadvantages Dependency Scanning](#disadvantages-of-dependency-scanning)
- [Using Safety for Dependency Scanning](#using-safety-for-dependency-scanning)
- [Best Practices for Dependency Scanning](#best-practices-for-dependency-scanning)
- [Recommendation/Conclusion](#recommendationconclusion)
- [References](#references)
- [Contact Information](#contact-information)


## 🎯 Purpose
This document aims to provide a comprehensive overview of dependency scanning in Python project like we have or ```Attendance-API``` , emphasizing its importance in Continuous Integration (CI) pipelines.

## 📖 Introduction
Continuous Integration (CI) is a crucial practice in modern software development, ensuring code quality and security throughout the development lifecycle. One critical aspect of CI for Python projects is dependency scanning, which helps identify and mitigate potential vulnerabilities in third-party packages used in your project.

## 🔍 What is Dependency Scanning?
Dependency scanning is the process of automatically analyzing a project's dependencies to identify known security vulnerabilities, outdated packages, and potential licensing issues. For Python projects, this typically involves examining the `requirements.txt`, `pyproject.toml`, or `poetry.lock` files to check the versions of installed packages against databases of known vulnerabilities.

## ❓ Why Perform Dependency Scanning?

| **Reason**                     | **Description**                                                                                      |
|--------------------------------|------------------------------------------------------------------------------------------------------|
| **🔒 Security**                | Identify and address known vulnerabilities in your dependencies before they can be exploited.      |
| **⚖️ Compliance**              | Ensure your project adheres to licensing requirements and organizational policies.                   |
| **🔧 Maintenance**             | Keep dependencies up-to-date, reducing technical debt and potential compatibility issues.           |
| **📉 Risk Management**         | Proactively manage and mitigate risks associated with third-party code.                             |

## 🛠️ Different Tools for Python Dependency Scanning and it's Comparision

Here’s a simplified comparison of Python dependency scanning tools with emojis for a more engaging presentation:

| **Tool**      | **Description**                                                   | **Key Features**                                             | **License**             | **Integration**                  | **Pros**                                                | **Cons**                                               |
|---------------|-------------------------------------------------------------------|-------------------------------------------------------------|-------------------------|----------------------------------|---------------------------------------------------------|--------------------------------------------------------|
| **1. Safety 🔒** | Checks for vulnerabilities in dependencies.                       | - Scans against PyPI for vulnerabilities. <br> - Generates reports. | Open Source (MIT)      | CLI, CI/CD (e.g., GitHub Actions) | - Lightweight & easy to use. <br> - Focused on security. | - Limited to known vulnerabilities. |
| **2. Snyk 🛡️**   | Comprehensive security solution for open-source dependencies.   | - Monitors for vulnerabilities. <br> - Provides fix suggestions. | Free & Paid Plans      | CLI, CI/CD, IDE plugins          | - Robust vulnerability database. <br> - Offers remediation steps. | - Advanced features may require payment.          |
| **3. PyUp ⬆️**   | Automates dependency monitoring and updates.                     | - Automates updates. <br> - Provides security alerts.      | Free & Paid Plans      | GitHub, GitLab integration       | - Great for managing updates. <br> - Useful for security and compatibility. | - Can generate many update PRs. |
| **4. Dependabot 🤖** | Automatically suggests dependency updates on GitHub.         | - Automated PRs for updates. <br> - GitHub integration.     | Free for public repos   | GitHub                          | - Seamless GitHub integration. <br> - Automates updates. | - Limited to GitHub. <br> - May create frequent PRs. |
| **5. pip-audit 📋** | Audits installed packages for vulnerabilities.                 | - Checks installed packages. <br> - Provides detailed reports. | Open Source (Apache 2.0) | CLI, CI/CD (e.g., GitHub Actions) | - Simple and lightweight. <br> - Focuses on installed packages. | - Only checks installed packages; no update monitoring. |

## ✅ Advantages of Dependency Scanning

| **Advantage **                | **Description**                                                                                             |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **🔍 Early Detection**                    | Identify security issues in dependencies before they can be exploited.                                     |
| **🤖 Automated Checks**                   | Integrate security into your CI/CD pipeline, reducing manual effort.                                       |
| **⚖️ Compliance Support**                 | Helps maintain compliance with security standards and regulations.                                          |
| **⚠️ Update Conflicts**                   | Suggested security updates may conflict with other dependencies or application requirements.                |
| **📊 False Positives**                    | Some tools may report vulnerabilities that don't apply to your specific use case.                          |

## 🌟 Disadvantages of Dependency Scanning

| **Disadvantage**                        | **Description**                                                                                             |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **⚠️ Update Conflicts**                 | Suggested security updates may conflict with other dependencies or application requirements.                |
| **📊 False Positives**                  | Some tools may report vulnerabilities that don’t apply to your specific use case.                           |
| **🕒 Time-Consuming**                   | Scanning large projects with many dependencies can be slow and time-consuming.                              |
| **💻 Limited Context**                  | Tools may not always understand how a dependency is being used in your specific application.                |
| **🔧 Maintenance Overhead**             | Regularly updating and managing dependency scanning tools requires extra effort.                            |
| **💸 Additional Costs**                 | Some advanced dependency scanning tools or features might come with extra costs.                            |


## 🛡️ Best Practices for Dependency Scanning

| **Best Practice**                     | **Description**                                                                                      |
|---------------------------------------|------------------------------------------------------------------------------------------------------|
| **Run Scans Regularly**              | Make dependency scanning a daily CI task.                                                           |
| **Update Dependencies Frequently**    | Keep packages current.                                                                                |
| **Pin Versions**                      | Specify exact package versions for consistency.                                                      |
| **Use Virtual Environments**          | Avoid dependency conflicts.                                                                          |
| **Monitor Vulnerability Alerts**      | Stay informed of new risks.                                                                          |

## 💼 Recommendation/Conclusion

In my Attendance API microservice, I recommend using Safety for its lightweight and efficient vulnerability scanning capabilities, ensuring that all installed dependencies are regularly checked against known vulnerabilities. This proactive approach enhances the security of the microservice, safeguarding user data and maintaining system integrity.


## 📚 References

| **Reference**                                                  | **Link**                                                                                          |
|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Safety Documentation**                                      | [Safety Docs](https://pyup.io/safety/)                                                           |
| **Snyk Python Documentation**                                 | [Snyk Docs](https://docs.snyk.io/products/snyk-open-source/language-and-package-manager-support/snyk-for-python) |
| **Python-CI POC**                           | [POC Doc](https://github.com/mygurukulam-p10/Documention/tree/main/Application%20CI%20Design/Python%20CI%20Checks/Dependency-Scanning-POC)                          |
| **pip-audit Documentation**                                   | [pip-audit Docs](https://pypi.org/project/pip-audit/)                                          |
| **OWASP Dependency-Check**                                   | [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)                       |

## 📞 Contact Information
For more information on how to implement CI or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |
