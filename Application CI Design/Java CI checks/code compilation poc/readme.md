## Proof of Concept (POC) for Code Compilation

## Table of Contents
+ [Introduction](#Introduction)
+ [ System Requirements](#System-Requirements)
+ [Build-Time Dependency](#build-time-dependency)
+ [Run Time Dependency](#run-time-dependency)

+ [Proof of Concept](#Pre-requisite)

+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [ References](#references)

  ## Introduction 
* 


## ⚙️ Pre-requisites

- java
- Maven

## System Requirements
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


## Best Practices
| Best Practice                   | Description                                               |
|----------------------------------|-----------------------------------------------------------|
| **Use Descriptive Names**       | Ensure class and file names are descriptive and follow Java naming conventions. |
| **Organize Packages**           | Structure your code into packages for better management and modularity. |
| **Comment Your Code**           | Use comments to explain complex logic and improve readability. |
| **Regularly Update JDK**       | Keep your JDK updated to leverage the latest features and improvements. |
| **Use Build Tools**             | For larger projects, consider using Maven or Gradle to manage dependencies and builds. |

## Recommendation
Maven is a robust choice for Java projects, especially in enterprise settings where standardization, dependency management, and integration with CI/CD practices are crucial. Its established ecosystem and community support further enhance its viability as a go-to build tool. If you prioritize a structured and maintainable approach to building Java applications, Maven is a compelling option.

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
