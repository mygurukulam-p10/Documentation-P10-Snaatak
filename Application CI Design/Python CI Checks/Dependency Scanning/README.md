![image](https://github.com/user-attachments/assets/1da54ff0-a4e1-4910-8c19-d1ffdbe4f1b3)


# 🐍 Python CI Checks: 🔍 Dependency Scanning


 ## 📚 Table of Contents
Purpose
Introduction
What is Dependency Scanning?
Why Perform Dependency Scanning?
Different Tools for Python Dependency Scanning and it's Comparision
Advantages and Disadvantages of Dependency Scanning
Proof of Concept: Using Safety for Dependency Scanning
Best Practices for Dependency Scanning
Recommendation/Conclusion
References
Contact Information


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

## ✅ Advantages and Disadvantages of Dependency Scanning

| **Advantage/Disadvantage**                | **Description**                                                                                             |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **🔍 Early Detection**                    | Identify security issues in dependencies before they can be exploited.                                     |
| **🤖 Automated Checks**                   | Integrate security into your CI/CD pipeline, reducing manual effort.                                       |
| **⚖️ Compliance Support**                 | Helps maintain compliance with security standards and regulations.                                          |
| **⚠️ Update Conflicts**                   | Suggested security updates may conflict with other dependencies or application requirements.                |
| **📊 False Positives**                    | Some tools may report vulnerabilities that don't apply to your specific use case.                          |

Note :- I am using ```safety``` as a Dependency Scanning tool in my POC.

## 💡 Proof of Concept: Using Safety for Dependency Scanning

Safety is a command-line tool that checks your installed dependencies for known security vulnerabilities. Here's how I am integrate it into my microservice of **ATTENDANCE-API**:

1. **Install Safety**:
   ```bash
   pip install safety
   ```
2. **Go to Attendance-API**
   ```
   cd attendance-api/
   ```
  
2. **Run a scan**:
  First Run the scan on ``` pyproject.toml``` 
   ```
   safety check -r pyproject.toml 
   ```
![image](https://github.com/user-attachments/assets/54417b55-4943-46e8-aa1b-4c61967b62ff)

  Now Run the scan on ```poetry.lock```
  ```
  safety check -r poetry.lock
  ```

![image](https://github.com/user-attachments/assets/62fcc804-4260-4529-ac2e-02e69df57197)
![image](https://github.com/user-attachments/assets/dece325d-abbc-4a78-a744-f713666dca35)
![image](https://github.com/user-attachments/assets/e257b470-898c-4e19-b479-2a2714b21d20)


This configuration will run a safety check on every request, scanning the `pyproject.toml` and `poetry.lock` file for known vulnerabilities as in our ```ATTENDANCE-API``` , We are having these 2 files.

![image](https://github.com/user-attachments/assets/732e63c8-d8d9-4aa7-afd3-ba304a1dea5f)
![image](https://github.com/user-attachments/assets/dd51547e-3445-44e4-81da-e09368ec99a1)


## 🛡️ Best Practices for Dependency Scanning

| **Best Practice**                     | **Description**                                                                                      |
|---------------------------------------|------------------------------------------------------------------------------------------------------|
| **Run Scans Regularly**              | Make dependency scanning a daily CI task.                                                           |
| **Update Dependencies Frequently**    | Keep packages current.                                                                                |
| **Pin Versions**                      | Specify exact package versions for consistency.                                                      |
| **Use Virtual Environments**          | Avoid dependency conflicts.                                                                          |
| **Monitor Vulnerability Alerts**      | Stay informed of new risks.                                                                          |

## 💼 Recommendation/Conclusion
Implementing dependency scanning in your Python CI pipeline is crucial for maintaining the security and stability of your project. While there are several tools available, each with its strengths, the choice depends on your specific needs:

- For open-source projects or those with basic needs, Safety or pip-audit provide good, free options with easy CI integration.
- For enterprise-level projects requiring comprehensive analysis across multiple languages, Snyk offers advanced features and detailed remediation advice.
- For GitHub-based projects, Dependabot provides native integration and automated pull requests for updates.
- For teams looking for a Python-specific, managed solution, PyUp offers detailed analysis and update recommendations.

Regardless of the tool chosen, regular dependency scanning should be an integral part of your development process. It's recommended to start with a basic tool like Safety and evolve your strategy as your project's needs grow, potentially incorporating multiple tools for comprehensive coverage.



## 📚 References

| **Reference**                                                  | **Link**                                                                                          |
|---------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Safety Documentation**                                      | [Safety Docs](https://pyup.io/safety/)                                                           |
| **Snyk Python Documentation**                                 | [Snyk Docs](https://docs.snyk.io/products/snyk-open-source/language-and-package-manager-support/snyk-for-python) |
| **GitHub Dependabot Documentation**                           | [Dependabot Docs](https://docs.github.com/en/code-security/dependabot)                          |
| **pip-audit Documentation**                                   | [pip-audit Docs](https://pypi.org/project/pip-audit/)                                          |
| **OWASP Dependency-Check**                                   | [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)                       |

## 📞 Contact Information
For more information on how to implement CI or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |
