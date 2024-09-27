# 🐹 Go CI Checks - Dependency Scanning

|  Author        | Created on |  Version  | Last updated by   |   Last edited on   |
|----------------|------------|-----------|-------------------|--------------------|
| Abhinav Singh  |  23-09-24  | version 2 |   Abhinav Singh   |      26-09-24      |


 ## 📚 Table of Contents

1. [Purpose](#purpose)
2. [What is Dependency Scanning](#what-is-dependency-scanning)
3. [Different Tools for Go Dependency Scanning](#different-tools-for-go-dependency-scanning)
4. [Advantages and Disadvantages of Dependency Scanning](#advantages-and-disadvantages-of-dependency-scanning)
5. [Best Practices for Dependency Scanning](#best-practices-for-dependency-scanning)
6. [Conclusion](#conclusion)
7. [Reference](#reference)
8. [Contact Information](#contact-information)

## Purpose

This document provides a comprehensive guide on implementing effective dependency scanning in Go projects, focusing on the utilization of Snyk as a robust tool for identifying and addressing vulnerabilities within your software's dependencies. The goal is to equip you with the knowledge and practical steps to ensure the security of your Go applications throughout the development and deployment lifecycle.


## What is Dependency Scanning

Dependency scanning is a security practice that involves analyzing an application's dependencies (external libraries, frameworks, and packages) for known vulnerabilities. These dependencies, while often essential for development efficiency, can introduce security risks if not properly managed.


| **Reason**              |             **Description**                                |
|--------------------------------|-----------------------------------------------------|
| **🔐Security**                | Identify and fix vulnerabilities in your dependencies. |
| **⚖️Compliance**              | Ensure compliance with security and licensing policies.|
| **🔧Maintenance**             | Keep dependencies updated to avoid technical issues.|
| **📉 Risk Management**         | Proactively manage risks from third-party code.  |

## Different Tools for Go Dependency Scanning

| Tool            | Description                                       | Key Features                                      | Pros                                         | Cons                                        |
|-----------------|---------------------------------------------------|--------------------------------------------------|----------------------------------------------|---------------------------------------------|
| 🛡️ **Snyk**       | Scans for security issues in open-source code.    | - Monitors `go.mod` <br> - Suggests fixes         | - Large database of issues <br> - Fix recommendations | - Some features require payment             |
| 🤖 **Dependabot** | Automatically updates dependencies in GitHub.    | - Creates PRs for updates <br> - Works with GitHub | - Automates updates                          | - Only works with GitHub                    |
| 🚨 **GoVulnCheck** | Scans Go modules for security vulnerabilities.   | - Checks `go.mod` <br> - Simple reports           | - Made for Go <br> - Easy to use             | - Limited features                          |
| 🔍 **FOSSA**      | Scans for security and license issues.           | - Checks license compliance <br> - Security reports | - Good for projects needing compliance       | - Too complex for smaller projects          |



## Advantages and Disadvantages of Dependency Scanning

| Benefit                        | Drawback                                      |
|---------------------------------|-----------------------------------------------|
| **Security:** Detects vulnerabilities           | **False Positives:** Unnecessary alerts              |
| **License Compliance:** Ensures legal use       | **Resource Intensive:** High CPU/memory usage        |
| **Reduces Manual Effort**                       | **Over-Patching:** Upgrades may break functionality  |
| **Improves Dependency Hygiene**                 | **Frequent Tool Updates:** Tools need regular updating |


# Best Practices for Dependency Scanning

| Best Practice            | Description                                                                   |
|--------------------------|-------------------------------------------------------------------------------|
| **🏃‍♂️Run Scans Regularly**   | Schedule dependency scans frequently to catch new vulnerabilities.            |
| **📌Pin Versions**          | Pin exact versions of dependencies to ensure consistent builds.               |
| **🔄Update Dependencies**   | Regularly update dependencies to stay secure.                                 |
| **🗂️Use Go Modules**        | Use Go modules (`go.mod`) to manage dependencies efficiently.                |

## Conclusion

For Go projects like **Employee API**, **Snyk** is an outstanding tool for dependency scanning in CI pipelines. It efficiently detects vulnerabilities in third-party libraries, helping to keep the project secure over time. By integrating **Snyk** into our CI process, we can automate these scans and proactively address potential risks, ensuring the ongoing safety and reliability of our application.

## Reference

| Title                                 | Link                                                                                           |
|---------------------------------------|------------------------------------------------------------------------------------------------|
| Dependency Scanning POC | https://github.com/mygurukulam-p10/Documention/tree/main/Application%20CI%20Design/GoLang%20CI%20Checks/Dependency%20scanning%20POC |
|    Snyk Docs  | (https://docs.snyk.io/) |
|    GoVulnCheck Docs     |   (https://documentation.defectdojo.com/integrations/parsers/file/govulncheck/) |

## Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

|  Name   | Email Address                                  |
|---------|------------------------------------------------|
| Abhinav | abhinav.singh.snaatak@mygurukulam.co           |
