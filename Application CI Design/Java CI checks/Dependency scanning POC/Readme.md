
# Proof of Concept (POC) for Dependency-Check

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 22-09-24    | version 1  | Amit Nagar      | 23-09-24       |


## Table of Contents
+ [Introduction](#Introduction)
+ [OWASP](#owasp-dependency-check)
+ [Proof of Concept](#Pre-requisite)
+ [Suppressing dependencies](#dependency-suppression)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***
## Introduction 
* Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on. By scanning for known vulnerabilities in these dependencies, you can proactively address potential security risks and keep your applications robust and secure. This document will guide you through a Proof of Concept (PoC) for setting up and utilizing OWASP Dependency-Check to perform comprehensive dependency scanning in your projects.

***
## OWASP Dependency-Check
OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects. 

*** 

## Flow Diagram



***
## Proof of Concept (PoC) - Setting Up Dependency Scanning
### 1. Pre-requisite

**1.1) Java**

* Ensure that you have Java installed on your system. The project requires Java version 17. If you don't have it installed, you can download and install it from the official Java website: [Java Downloads](https://www.oracle.com/java/technologies/downloads/) or use your preferred package manager.

**1.2) Maven**
* Make sure to have Maven installed on your system. It is a powerful tool used for managing project dependencies. If you don't have Maven installed, please follow the installation instructions for your operating system, which can be found on the official Apache Maven website: [Maven Installation Guide](https://maven.apache.org/install.html).
![Screenshot from 2024-09-23 01-31-39](https://github.com/user-attachments/assets/67296703-676f-43ea-8ee6-c8ed0a496e77)

**1.3) Internet Access to retreive NVD Data**

* The NVD is a comprehensive source of vulnerability information. Dependency-Check can use this data to identify known vulnerabilities in your project's dependencies. It can be configured to fetch data from the NVD's Common Vulnerabilities and Exposures (CVE) database during the analysis process. This helps ensure that the tool has up-to-date information about known vulnerabilities.


  
### 2. Configuration

* To enable the `OWASP Dependency-Check` plugin in your Maven project, add the following configuration to your pom.xml file. Ensure this configuration is placed within the `<build>` section

```xml
            <!-- Add the OWASP Dependency-Check plugin -->
            <plugin>
                <groupId>org.owasp</groupId>
                <artifactId>dependency-check-maven</artifactId>
                <version>10.0.4</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```
### 3. Generate Reports

* This ensures a clean build of your project before checking for vulnerabilities, run the following Maven command to ensure a clean build:
* To generate a comprehensive report for your project, run the following Maven command in your terminal:

```shell
mvn dependency-check:check
```

> [!NOTE]
> You can use dependency check arguments based on your requirements. These arguments allow you to customize the behavior of the tool according to your project's needs. They can be used to control aspects such as output format, updating data feeds, etc. You can find detailed information by visiting the following link: [Dependency-Check Arguments](https://jeremylong.github.io/DependencyCheck/dependency-check-cli/arguments.html).

### 4. Verification

* Navigate to the build artifacts or workspace. Locate the generated Dependency-Check reports in the `target` folder. They are typically available in multiple formats (JSON, HTML, XML). Ensure that vulnerabilities are correctly identified. If you configured multiple report formats , explore each format to understand the data presentation.


![Screenshot from 2024-09-23 01-36-59](https://github.com/user-attachments/assets/400afdff-462b-436d-b15d-ad213019f60a)



## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


