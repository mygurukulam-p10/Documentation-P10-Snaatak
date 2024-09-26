# 🐹 Go CI Checks - Dependency Scanning POC


 ## 📚 Table of Contents

1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Step by Step Guide to Perform Dependency scanning](#step-by-step-guide-to-perform-dependency-scanning)
4. [Conclusion](#conclusion)
5. [Reference](#reference)
6. [Contact Information](#contact-information)

## Purpose

🎯
This POC explains how to perform dependency scanning for Go projects, highlighting the use of Snyk as a key tool for identifying vulnerabilities during Continuous Integration (CI).

## Introduction

📖
In Go projects, scanning for vulnerable dependencies is essential for maintaining security. Dependency scanning in CI pipeline helps detect potential risks in the external libraries that the project relies on, ensuring that codebase stays secure.

## Step by Step Guide to Perform Dependency scanning

**1. Create an account on **snyk****

You can login using your google account or any other account.

![image](https://github.com/user-attachments/assets/7e615ac1-1b42-4ac6-a5f7-24d33c413532)

**2. Download a standalone executable of Snyk CLI  for your platform and make it executble with below commands
-**

'''
curl https://static.snyk.io/cli/latest/snyk-linux -o snyk
chmod +x ./snyk
mv ./snyk /usr/local/bin/ 
'''

![image](https://github.com/user-attachments/assets/1b1918fc-094d-41ec-94b6-5bdf940c8818)

**3.Use command "snyk auth" to authenticate with your account**

![image](https://github.com/user-attachments/assets/f2f5d813-3ac5-4ff3-8943-36d4b68b8ed2)

**4. Choose Grant app access to  provide access**

![image](https://github.com/user-attachments/assets/9f8eae5e-ae08-421b-b61a-f42c22adbc5f)

![image](https://github.com/user-attachments/assets/f710ee1d-2fae-4266-b620-c2071083d8ca)

**5. Navigate to your project directory and use "snyk test" command to scan the project files**

![image](https://github.com/user-attachments/assets/683b9901-341b-4c71-9a41-92824c4a9171)

![image](https://github.com/user-attachments/assets/3ce00cf7-e080-4b7c-b78a-56adf8932b1f)

**6. You can see reports of your test by opening links provided in the output**
![image](https://github.com/user-attachments/assets/2c65a9de-75d3-448e-ac08-016d06e3b777)

## Conclusion

This POC demonstrated how to perform dependency scanning for Go projects using Snyk. Vulnerabilities in external libraries can be easily identified and managed, ensuring the project's security. The guide covers setting up Snyk, authenticating, and scanning your project, allowing teams to continuously monitor and mitigate risks throughout development, maintaining a secure codebase.

## Reference

| Title                                 | Link                                                                                           |
|---------------------------------------|------------------------------------------------------------------------------------------------|
|    Snyk Docs  | (https://docs.snyk.io/) |
|    GoVulnCheck Docs     |   (https://documentation.defectdojo.com/integrations/parsers/file/govulncheck/) |

## Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

|  Name   | Email Address                                  |
|---------|------------------------------------------------|
| Abhinav | abhinav.singh.snaatak@mygurukulam.co           |
