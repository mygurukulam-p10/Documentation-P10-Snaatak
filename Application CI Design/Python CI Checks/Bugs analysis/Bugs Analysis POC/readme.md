# 🛡️ Bandit - Python Security Linter

## 📑 Table of Contents
- [📖 Introduction](#-introduction)
- [✨ Key Features](#-key-features)
- [📋 Pre-requisites](#-pre-requisites)
- [⚙️ Installing Bandit](#️-installing-bandit)
- [🚀 Proof of Concept (POC)](#-proof-of-concept-poc)
- [📊 Bandit Report Analysis](#-bandit-report-analysis)
- [🏁 Conclusion](#-conclusion)
- [📞 Contact Information](#-contact-information)
- [🔗 References](#-references)

## 📖 Introduction
Bandit is a tool that scans Python code to find common security issues. It processes each file, builds an abstract syntax tree (AST), and runs plugins against the AST nodes to detect vulnerabilities. After scanning, Bandit generates a report highlighting any issues found.

## ✨ Key Features
- 🐍 **Language Compatibility**: Supports Python 2.x and 3.x.
- 🔍 **Static Analysis**: Analyzes code without execution to find vulnerabilities.
- 🔌 **Plugin Architecture**: Extendable with custom checks.
- 🛠️ **Common Vulnerabilities**: Detects issues like hardcoded secrets and unsafe `eval()` use.
- 🔒 **Security Checks**: Identifies potential SQL injection, XSS, and command injection flaws.
- 🔗 **Integration**: Easily integrates with CI/CD pipelines for automated checks.
- 📊 **Extensive Reporting**: Generates detailed reports with severity levels and issue locations.
- ⚙️ **Configurability**: Offers customizable options to adjust analysis settings.
- 💻 **Command Line Interface**: Simple CLI for easy use.
- 🚀 **Active Development**: Maintained by the OpenStack Security Project.
- 🆓 **Open Source**: Available under Apache 2.0 license.

## 📋 Pre-requisites
- 🐍 **Python 3**: Bandit requires Python 3 to run.

## ⚙️ Installing Bandit
Install Bandit using pip:

```
pip install bandit
```
![image](https://github.com/user-attachments/assets/09caeabf-787c-4b76-a92b-a23324764c61)

**Once Bandit is installed, you can start using it to scan your Python code.**

🧑‍💻 Using Bandit
To scan all Python files in a directory, use:

**Using dot (.) notation it will scan all the Python files which are inside that directory:**
```
bandit -r .
```

If you want to scan any specific file, you can enter the path of that Python file:

```
bandit -r /path/to/your/code.py
```

Include low-severity issues:

```
bandit -r . -ll
```

Set a severity threshold:
**This command will only report issues with a severity level of MEDIUM or higher.**
```
bandit -r /path/to/your/code -s MEDIUM
```



You can also exclude certain files or directories from the scan by using the -x option followed by the path to exclude:

```
bandit -r . -x some_directory/
```
🚀 ### Proof of Concept (POC)###
Example command:
```
bandit -r /home/Brij/sanatak/Python/attendance-api$
```
📊 Bandit Report Analysis

![image](https://github.com/user-attachments/assets/4aaac4e3-8548-412d-87c7-2a63e8fc458c)

![image](https://github.com/user-attachments/assets/0589bd44-5649-4994-98f3-19efab36821e)


![image](https://github.com/user-attachments/assets/3a726e48-39bd-442e-b68c-a5509852367c)



![image](https://github.com/user-attachments/assets/769f7fb3-f390-4a49-86db-bd8768a5260d)




Bandit reports include:

| Report | Description                                          |
|-----------|------------------------------------------------------|
|📁 File Paths |Files analyzed.|
|🔢 Line Numbers| Where issues were found.|
|⚠️ Issue Severity Levels| |Low, Medium, High.|
|📝 Issue Descriptions | Details of detected vulnerabilities.|
|📄 Review Reported Issues| Review the reported issues and their severity.|
|🚨 Prioritize Fixes| Prioritize fixing high-severity issues.|
|🔄 Refactor Code | Address vulnerabilities by refactoring code.|
|🔁 Automate Checks| Integrate Bandit into CI/CD pipelines for continuous security checks.|

🏁 Conclusion
Bandit helps developers identify security issues in Python applications, making it a valuable tool to improve code security.


