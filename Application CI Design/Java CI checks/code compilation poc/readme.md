# Proof of Concept (POC) for Code Compilation for Java
![java](https://github.com/user-attachments/assets/b07cbf43-b8ff-4e96-a6aa-7177d0be4ad4)


  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 19-09-24 | version 1 | Vinay Bansal | 29-09-24 |

## Purpose
We are preparing this document so that we can easily provide a completed guide to step code compilation which is designed in Java to manage salary-api information.

## Table of Contents
- [Introduction](#Introduction)
- [Pre-requisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Build-Time Dependency](#build-time-dependency)
- [Run-Time Dependency](#run-time-dependency)
- [Architecture](#architecture)
- [Step-by-step Installation](#step-by-step-installation)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [ References](#references)

## Introduction 
* This document will guide you through a Proof of Concept (PoC) for setting up and compiling a Maven project. We will cover the necessary prerequisites, including Java and Maven installation, as well as the basic project structure.


##  Pre-requisites

- Java
- Maven

## System Requirements
| Hardware Specifications | Minimum Requirement  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 2 GB                    |
| Disk                     |5 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


##  Build-Time Dependency

| 🛠️ Name | 📦 Version | 📄 Description |
|---------|------------|----------------|
| **Maven** | 3.+      | Simplifies build management, project documentation, and dependency management. |

---

##  Run-Time Dependency

| 🚀 Name | 📦 Version | 📄 Description          |
|---------|------------|--------------------------|
| **Java** |  17 for Spring Boot 3.1.1        | Required to run the built Java application. |


## Architecture
<img width="605" alt="image" src="https://github.com/user-attachments/assets/d2bfd5ac-4075-4e22-a360-993f7a1017c6">

##  Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```

### Step 2: Change Directory
Change Directory to where your code is
```
cd salary-api
```

### Step 3: now we have to do Code Compilation
This command compiles the source code of the project according to the settings defined in the pom.xml file.
```
mvn compile
```
![compile](https://github.com/user-attachments/assets/7a41dd76-d90a-40bf-a91a-c0bbe726cb70)
- When you see a “BUILD SUCCESS” message after running the mvn compile command in Maven, it means that the source code of your project has been successfully compiled without any errors and your project’s source code is now ready for the next phases, such as testing or packaging.


## Conclusion
The mvn compile command is a fundamental part of the Maven build lifecycle, responsible for compiling the source code of a Java project. By following a structured process, Maven ensures that all dependencies are resolved, and the code is compiled efficiently. This makes Maven an essential tool for managing and building Java projects, especially in enterprise environments where standardization and integration with CI/CD practices are crucial.

## Contact Information

| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## References
For further reading and resources on GitOps, check out the following:

| Links | Descriptions|
|------|---------------------|
|Oracle Java Documentation|https://docs.oracle.com/en/java/|
|Document |https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Java%20CI%20checks/code%20compilation%20doc/readme.md|
