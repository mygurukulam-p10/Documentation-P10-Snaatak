# Bug Analysis for Java - Shared Library 

![image](https://github.com/user-attachments/assets/bfb8783c-372b-4822-9602-12066a234e99)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 14-10-2024  | Version 1  | Vinay Bansal    | 15-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration to Bug Analysis](#-steps-to-configuration-to-bug-analysis)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Shared Library for Bugs analysis in Java. Jenkins, as a popular automation server, supports a variety of build configurations. One of the critical aspects of Java CI checks is Bugs Analysis, which involves identifying, analyzing, and resolving bugs in the code to ensure software quality and reliability


---

## ⚙ Pre-requisites

| **Requirement** | **Description**                                             |
|------------------|------------------------------------------------------------|
| **Jenkins**      | Ensure you have a Jenkins instance running.                |
| **Java**         | Required to run the built Java application.                |
| **Maven**        | Simplifies build management.                                |
| **SpotBugs**     | A static analysis tool that finds bugs in Java programs by analyzing bytecode. |

## 🔍 System Requirements 
[here](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/blob/main/CI%20Implementation/Java%20-%20Declarative%20Jenkins%20Pipeline/Static%20code%20analysis/readme.md#-system-requirements)


## 💥 Steps to Configuration to Bug Analysis
### Understand Shared Library Syntax
```
(root)
+- src                     # Groovy source files
|   +- org
|       +- foo
|           +- Bar.groovy  # for org.foo.Bar class
+- vars
|   +- foo.groovy          # for global 'foo' variable
+- resources               # resource files (external libraries only)
|   +- org
|       +- foo
|           +- bar.json    # static helper data for org.foo.Bar
```
| Directory/File       | Description                                                   |
|----------------------|---------------------------------------------------------------|
| `src/`               | Contains Groovy source files, organized by packages.         |
| `src/org/`          | Package directory for organizational structure.              |
| `src/org/foo/`      | Sub-package for functionality related to `foo`.              |
| `src/org/foo/Bar.groovy` | Defines the `org.foo.Bar` class.                         |
| `vars/`              | Holds global variables and their documentation.              |
| `vars/foo.groovy`    | Global variable or function named `foo`.                     |
| `vars/foo.txt`       | Help documentation for the `foo` variable.                  |
| `resources/`         | Contains non-code files (like JSON) that support functionality. |
| `resources/org/`     | Package directory for resource organization.                 |
| `resources/org/foo/` | Sub-package for resources related to `foo`.                  |
| `resources/org/foo/bar.json` | Static helper data for the `org.foo.Bar` class.     |
### 1. 🚀 Open your Jenkins Dashboard.
![1](https://github.com/user-attachments/assets/59bb5e6e-68e1-4d41-8147-cd7acceeb2d8)

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Bug-analysis-shared`).
![image](https://github.com/user-attachments/assets/8ed91e15-f2a0-4db1-a9fa-5028e42168ac)


### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![image](https://github.com/user-attachments/assets/77b6469d-c1f6-48be-92c3-bb4a17aa4b7b)



### 4. 🚀 Create the repo for add vars file which will be using in pipeline script.
![image](https://github.com/user-attachments/assets/6ef8e548-2f8b-438d-afc4-82a9f5c538a9)



### 5. 🚀 Choose Pipeline as the job type-->Add your pipeline script for Unit Testing analysis in the pipeline script ...> add repo link & credintial, file path.
![image](https://github.com/user-attachments/assets/1729d1cc-070d-4c17-abfe-aa3ba12bfedd)



### 6. 🚀 Then Click on build to run the pipeline to perform
<img width="952" alt="build" src="https://github.com/user-attachments/assets/c82d9cba-0169-4495-8193-2cadac88f833">


### 7.🚀 Now we are able to see build complete-
![image](https://github.com/user-attachments/assets/eae26743-8717-477f-94f9-ba11ef9c5c48)


### 8.🚀 Click on Console Output to see the complete build.
![image](https://github.com/user-attachments/assets/6b9b1067-61e2-4a55-966c-00860639a822)
![image](https://github.com/user-attachments/assets/69468815-81a1-4244-a980-6ccab1395d28)


### 9.🚀 Review the stages of the build process in the console output.
![image](https://github.com/user-attachments/assets/ccf88317-a92b-4ba9-acab-d0e5c42285e3)



## 📛 Conclusion
We are using 'spotbugs' plugin in the current project. This shared library streamlines bug analysis in Java by leveraging powerful tool, offering reusable and modular components for detecting issues. It promotes consistency, reduces redundant code, and simplifies the integration of automated bug detection in CI/CD pipelines like Jenkins. By adopting this library, teams can enhance productivity and maintain high-quality code across multiple projects.


##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

---
## 📚 References
| Links | Descriptions|
|------|---------------------|
|https://tinyurl.com/66cr6xeh|SpotBugs Maven Plugin |
|https://tinyurl.com/56k8jfwp|(POC): Bug Analysis|
