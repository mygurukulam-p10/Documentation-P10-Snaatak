

# 🐞 Scripted Pipeline: Credential Scanning

| ✍️ **Author**      | 📅 **Created on**  | 📌 **Version**    | 📝 **Last updated by** | 📅 **Last edited on** |
|-------------------|--------------------|-------------------|-----------------------|-----------------------|
| Brij Singh      | 09-10-2024          | Version 1         | Brij Singh            | 09-10-2024            |
---

## 📑 Table of Contents
1. [Introduction](#introduction)
2. [Why Scripted Pipeline](#why-scripted-pipeline)
3. [Flow Diagram](#flow-diagram)
4. [Pre-requisites](#pre-requisites)
5. [Setup of Credential Scanning](#setup-of-credential-scanning)
6. [Jenkinsfile](#jenkinsfile)
7. [Conclusion](#conclusion)
8. [Contact Information](#contact-information)
9. [Resources and References](#resources-and-references)

---

## 📖 Introduction
Scripted Pipeline in Jenkins allows users to define CI/CD pipelines using the **Groovy** scripting language. This approach offers flexibility and customization for defining complex workflows. It provides an imperative, programmatic approach where scripts are executed sequentially, with direct access to Jenkins APIs for advanced automation.

### 🔐 Credential Scanning Tool Used: GitLeaks
[GitLeaks](https://github.com/gitleaks/gitleaks) is a powerful open-source tool designed to scan Git repositories for sensitive information such as credentials, API keys, and passwords. It ensures that confidential data is not accidentally leaked in version-controlled codebases.

---

## ❓ Why Scripted Pipeline

| ⚙️ **Aspect**                  | 📝 **Description**                                                                                                                                                  |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **📜 Imperative Syntax**        | Pipelines are written as Groovy scripts, providing full control over execution flow for complex logic and dynamic behavior.                                        |
| **🔄 Programmatic Constructs**  | Allows usage of loops, conditions, variables, and functions for building highly customizable pipelines.                                                            |
| **🔧 Direct Access to APIs**    | Scripts can directly interact with Jenkins APIs for fine-grained automation and integration with external systems or plugins.                                      |
| **🔗 Extensibility**            | Enables defining custom functions and importing external libraries to enhance pipeline functionality and reusability.                                             |
| **🧰 Legacy Support**           | Widely adopted in environments with existing pipelines, offering familiarity and backward compatibility with legacy systems.                                      |
| **🎓 Learning Curve**           | Requires knowledge of Groovy syntax and Jenkins pipeline concepts, leading to a steeper learning curve, especially for newcomers.                                  |
| **🛠 Debugging and Maintenance**| The imperative approach can make debugging and maintenance more challenging, necessitating proper organization, documentation, and testing.                       |

---

## 📝 Flow Diagram
*Insert a flow diagram showing the steps of the Scripted Pipeline for credential scanning.*

---

## 🛠 Pre-requisites

| **Tool**   | **Version**  |
|------------|--------------|
| **🖥️ Jenkins**  | 2.426.3    |
| **🔍 Gitleaks** | 8.18.2     |

---

## 🔧 Setup of Credential Scanning
Follow this [document](#) for the complete setup.

*Insert relevant screenshots or additional details here.*

---

## 📝 Jenkinsfile

```groovy
node {
  // Checkout SCM
  stage('Checkout SCM') {
      git branch: 'main', url: 'https://github.com/OT-MICROSERVICES/employee-api.git'
  }

  // Download and Install Gitleaks
  stage('Download and Install Gitleaks') {
      sh 'wget https://github.com/gitleaks/gitleaks/releases/download/v8.18.2/gitleaks_8.18.2_linux_x64.tar.gz'
      sh 'tar xvzf gitleaks_8.18.2_linux_x64.tar.gz'
  }

  // Gitleaks Scan
  stage('Gitleaks Scan') {
       try {
          sh './gitleaks detect -r credScanReport'
      } catch (Exception e) {
          echo "Gitleaks scan failed. Archiving report."
          archiveArtifacts artifacts: 'credScanReport', allowEmptyArchive: true
          error 'Gitleaks scan failed'
      }
  }

  // Post-build actions
  cleanWs()
}


🔚 Conclusion
Scripted Pipeline is a powerful and flexible way to define Jenkins pipelines using Groovy scripting language. It is suitable for environments that require fine-grained control, advanced automation, and integration capabilities. However, it may involve a steeper learning curve and more complexity in debugging compared to Declarative Pipelines.


## 📧 Contact Information

| 👨‍💻 **Name**   | 📧 **Email Address**                                  |
|-----------------|-------------------------------------------------------|
| Brij Singh       | [Brij.singh.snaatak@mygurukulam.co](mailto:brij.singh.snaatak@mygurukulam.co) |

---

📚 Resources and References
📄 Description	🔗 Source
About Jenkins Pipeline (Generic Document)	Link
Credential Scanning POC Steps	Link
POC Generic Document	Link
Setup Jenkins	Link
Jenkinsfile	Link
Scripted vs Declarative Pipelines	Link
Credential Scanning	Link
