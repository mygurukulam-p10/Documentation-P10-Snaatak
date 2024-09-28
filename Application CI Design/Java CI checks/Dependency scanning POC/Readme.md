
# Proof of Concept (POC) for Dependency-Check

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 22-09-24    | version 1  | Amit Nagar      | 23-09-24       |


## Table of Contents
+ [Introduction](#Introduction)
+ [ System Requirements](#System-Requirements)
+ [Build Dependency](#Build-Dependency)
+ [Run Time Dependency](#Run-Time-Dependency)
+ [OWASP](#owasp-dependency-check)
+ [Proof of Concept](#Pre-requisite)
+ [Suppressing dependencies](#dependency-suppression)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [ References](#References)




***
## Introduction 
* Dependency scanning is a crucial aspect of modern software development, ensuring the security and reliability of your projects. This process involves identifying and managing the third-party libraries and frameworks your project depends on. By scanning for known vulnerabilities in these dependencies, you can proactively address potential security risks and keep your applications robust and secure. This document will guide you through a Proof of Concept (PoC) for setting up and utilizing OWASP Dependency-Check to perform comprehensive dependency scanning in your projects.

***

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | single-core              |
| RAM                      | 1GB                    |
| Disk                     | 10GB                   |
| OS                       | Ubuntu(22.04)          |

## Build Dependency

| Name                    | Version   | Description                                                                    |
|-------------------------|-----------|--------------------------------------------------------------------------------|
| Java                    | 17.0.12   | Required for Java-based build or runtime environments.                         |
| Maven                   | 3.6       | A build automation tool used primarily for Java projects.                     |
| OWASP Dependency-Check  | 10.0.4    | A software composition analysis tool that identifies project dependencies and checks for known vulnerabilities. |

## Run Time Dependency

| Name           | Version   | Description                                                                                   |
|----------------|-----------|-----------------------------------------------------------------------------------------------|
| Java           | 17.0.12   | Required for Java-based build or runtime environments.                                         |

## OWASP Dependency-Check
OWASP is an open-source tool widely utilized for identifying known vulnerabilities in project dependencies. This tool automatically analyzes dependencies and checks them against a comprehensive database of security vulnerabilities, including the National Vulnerability Database (NVD). It supports various programming languages and build tools, making it a versatile choice for enhancing the security of software projects. 

*** 

## Flow Diagram

![image](https://github.com/user-attachments/assets/8516e0a5-7979-405d-a246-f31efeb8e0a9)

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

***
## Dependency Suppression
* Suppression of a vulnerability in a dependency is typically done when you have assessed the specific context of your application and determined that a reported vulnerability doesn't pose a significant risk in your particular scenario.

Here's a step-by-step guide on how to suppress a vulnerability using the OWASP Dependency-Check tool:

**Step 1: Locate the Vulnerability** - Identify the specific vulnerability in your project by running the Dependency-Check tool. The tool will generate a report highlighting vulnerabilities in your dependencies.

**Step 2: Create a Suppression XML File** - Create a suppression XML file adhering to the OWASP Dependency-Check guidelines. This XML file will define which vulnerabilities should be ignored during subsequent scans. The file name can be anything (eg., `suppression.xml`, `dependency-suppression.xml`)

*suppression.xml:*

```
<?xml version="1.0" encoding="UTF-8"?>
<suppressions xmlns="https://jeremylong.github.io/DependencyCheck/dependency-suppression.1.3.xsd">
   
   <suppress>
   <notes><![CDATA[
   file name: jackson-databind-2.15.2.jar
   ]]></notes>
   <packageUrl regex="true">^pkg:maven/com\.fasterxml\.jackson\.core/jackson-databind@.*$</packageUrl>
   <cpe>cpe:/a:fasterxml:jackson-databind</cpe>
</suppress>
</suppressions>

```


**Step 3:  Save the suppression XML file in a location accessible to your project.

**Step 4: Add Configuration to pom.xml**
* Open your project's pom.xml file and locate the <plugins> section. Add the following configuration for the dependency-check-maven plugin:

```xml
            <plugin>
                <groupId>org.owasp</groupId>
                <artifactId>dependency-check-maven</artifactId>
                <version>10.0.4</version>
                <configuration>
                    <suppressionFile>/path/to/dependency-suppression.xml</suppressionFile>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>check</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>

```

* Replace /path/to/dependency-suppression.xml with the actual path to your suppression file.

**Step 5: Execute Dependency-Check** - Rerun the Dependency-Check tool as part of your Maven build. The suppression file will be automatically included, and the specified vulnerabilities will be ignored.

**Step 6: Confirm Suppression** - Review the Dependency-Check report to ensure that the suppressed vulnerability no longer appears in the list of identified security issues.

![Screenshot from 2024-09-23 15-38-38](https://github.com/user-attachments/assets/aa70141f-f663-4f2f-99e4-e295c960c33c)



***
## Conclusion

In conclusion, integrating OWASP Dependency-Check into your development process offers a proactive approach to identifying and mitigating potential security risks associated with third-party dependencies. By regularly scanning and analyzing your project dependencies, you can stay ahead of known vulnerabilities, ensuring the overall security and reliability of your software applications




## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## References
| Topic                          | Link                                                                                   |
|--------------------------------|----------------------------------------------------------------------------------------|
| OWASP Dependency Check         | [How It Works, Benefits, Pros & Cons](https://www.hackerone.com/knowledge-center/owasp-dependency-check-how-it-works-benefits-proscons) |
| OWASP Overview                 | [OWASP Official Site](https://owasp.org/)                                            |
                                           



