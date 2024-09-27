# Generic License Scanning Documentation

| Author      | Created on | Version   | Last updated by | Last edited on |
|-------------|------------|-----------|-----------------|----------------|
| Amit Nagar  | 24-09-24   | Version 1 | Amit Nagar      | 26-09-24       |

## Table Of Contents
- [Introduction](#introduction)
- [Why License Scanning?](#why-license-scanning)
- [License Scanning Tools](#license-scanning-tools)
- [Tool Comparison](#tool-comparison)
- [Tool Recommendation](#tool-recommendation)
- [Proof Of Concept: FOSSA](#proof-of-concept-fossa)
- [Advantages](#advantages)
- [Best Practices](#best-practices)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

---

## Introduction
- License scanning analyzes and identifies software licenses associated with code or components in a project.

---

## Why License Scanning?
- **Legal Compliance**: Ensures compliance with license terms and conditions.
- **OSS Management**: Identifies and manages licenses in open-source components.
- **Risk Mitigation**: Identifies legal risks associated with specific licenses.
- **Intellectual Property Protection**: Ensures compliance with license terms.
- **Security and Quality Assurance**: Evaluates security, quality, and reputation of components.

---

## License Scanning Tools
- **FOSSA**: Comprehensive license compliance and dependency analysis tool.
- **Black Duck**: Open-source security and license compliance solution.
- **WhiteSource**: Manages open-source components and license compliance.
- **Ninka**: Lightweight tool analyzing license text.
- **Licensee**: Ruby gem identifying licenses by analyzing license files.
- **ScanCode Toolkit**: Open-source license and metadata scanning toolkit.
- **LicenseFinder**: Manages dependencies and licenses in Ruby projects.
- **JFrog Xray**: Artifact analysis for security and license compliance.
- **FOSSology**: Open-source license compliance software system.

---

## Tool Comparison

| Feature / Aspect          | FOSSA                                             | Black Duck                                          | FOSSology                                          |
|---------------------------|---------------------------------------------------|----------------------------------------------------|---------------------------------------------------|
| **License Detection**     | Comprehensive across multiple languages           | Extensive across various languages and managers    | Focuses on source code analysis                    |
| **Vulnerability Scanning**| Open-source dependency scanning                    | Identifies vulnerabilities in OSS components       | Primarily license analysis, lacks security scanning|
| **Integration**           | Supports CI/CD tools, multiple workflows          | Integrates with popular DevOps tools               | Supports custom integrations through APIs         |
| **Ease of Use**           | User-friendly interface                           | Generally user-friendly                            | More technical interface                           |
| **Community Support**     | Active community support, regular updates         | Strong support, backed by Synopsys                 | Open-source with community contributions          |
| **Scalability**           | Scales for various project sizes                  | Enterprise-level scalability                       | Suitable for small to mid-sized projects          |
| **Customization**         | Flexible in reporting and policies                | Customizable policies and reporting                | Customization requires more technical expertise   |
| **Cost (Free Elements)**  | Free version with limited features                | Primarily commercial with trial options           | Open-source; support costs may apply              |

---

## Tool Recommendation
- **FOSSA** is recommended due to:
  - **Multi-language Support**: Comprehensive license detection across multiple languages.
  - **Vulnerability Scanning**: Robust scanning for security risks.
  - **User-Friendly Interface**: Easy navigation, integrates with CI/CD tools.
  - **Continuous Monitoring**: Monitors changes in licenses over time.

---

## Proof of Concept: FOSSA
- [FOSSA POC](https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Generic%20CI%20operation/License%20Scanning/%20License%20Scanning%20POC%20/Readme.md#contact-information)

---
## Advantages

| **Advantage**              | **Description**                                                                       |
|----------------------------|---------------------------------------------------------------------------------------|
| **Avoid Legal Issues**      | Ensures compliance with OSS and proprietary licenses.                                 |
| **Identify Risks Early**    | Detects license/security risks in OSS components.                                     |
| **Prevent Costly Remediation** | Early detection is more cost-effective.                                             |
| **Stay Up-to-Date**         | Continuous monitoring for license changes.                                            |

---

## Best Practices

| **Best Practice**           | **Description**                                                                       |
|-----------------------------|---------------------------------------------------------------------------------------|
| **Start Early**             | Include license scanning early in the development lifecycle.                          |
| **Update Databases**        | Keep license databases up-to-date.                                                    |
| **Integrate with CI/CD**     | Automate scans within the development workflow.                                       |
| **Automate Workflows**      | Use automated workflows for license approval.                                         |
| **Regular Audits**          | Regularly audit codebases for new dependencies.                                       |
| **Monitor License Changes** | Track changes as the project evolves.                                                 |

---

## Conclusion
- License scanning ensures legal compliance and mitigates risks in software development. Automating the process streamlines compliance and security while allowing teams to focus on development.

---

## Contact Information

| Name       | Email Address                                    |
|------------|--------------------------------------------------|
| Amit Nagar | [amit.nagar.snaatak@mygurukulam.com](mailto:amit.nagar.snaatak@mygurukulam.com) |

---

## References

| Tool        | Link                                                                   |
|-------------|------------------------------------------------------------------------|
| FOSSA       | [https://fossa.com](https://fossa.com)                                 |
| Black Duck  | [https://www.blackducksoftware.com](https://www.blackducksoftware.com) |
| Snyk        | [https://snyk.io](https://snyk.io)                                     |
| WhiteSource | [https://www.whitesourcesoftware.com](https://www.whitesourcesoftware.com) |
