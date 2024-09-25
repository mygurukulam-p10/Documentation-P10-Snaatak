# Proof of Concept (POC) for Code Compilation
![java](https://github.com/user-attachments/assets/b07cbf43-b8ff-4e96-a6aa-7177d0be4ad4)


  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 19-09-24 | version 1 | Vinay Bansal | 20-09-24 |

## Purpose
The purpose of this document is to provide a completed guide to step code compilation.

## Table of Contents
+ [Introduction](#Introduction)
- [⚙️ Pre-requisites](#pre-requisites)
- [🖥️ System Requirements](#system-requirements)
- [🛠️ Build-Time Dependency](#build-time-dependency)
- [🚀 Run-Time Dependency](#run-time-dependency)
- [📥 Step-by-step Installation](#step-by-step-installation)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [ References](#references)

  ## Introduction 
* This document will guide you through a Proof of Concept (PoC) for setting up and compiling a Maven project. We will cover the necessary prerequisites, including Java and Maven installation, as well as the basic project structure.


## ⚙️ Pre-requisites

- java
- Maven

## 🖥️ System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                    |
| Disk                     |20 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠️ Build-Time Dependency

| 🛠️ Name | 📦 Version | 📄 Description |
|---------|------------|----------------|
| **Maven** | 3.+      | Simplifies build management, project documentation, and dependency management. |

---

## 🚀 Run-Time Dependency

| 🚀 Name | 📦 Version | 📄 Description          |
|---------|------------|--------------------------|
| **Java** |  17 for Spring Boot 3.1.1        | Required to run the built Java application. |


## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```

### Step 2: Change Directory
```
cd salary-api
```

### Step 3: now we have to do Code Compilation
This command compiles the source code of the project according to the settings defined in the pom.xml file.
```
mvn compile
```
![compile](https://github.com/user-attachments/assets/7a41dd76-d90a-40bf-a91a-c0bbe726cb70)



## Conclusion
The choice of a build tool should be based on your specific project needs, team familiarity, and ecosystem compatibility. Each tool has unique strengths, and selecting the right one can significantly enhance your development workflow and project maintainability.


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
