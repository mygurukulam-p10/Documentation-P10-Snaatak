# POC: Bugs Analysis

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 25-09-2024         | 0.1       | Aayush Gaur  | Bugs Analysis              |


## Prerequisites
- Java Version 17 (As per project dependency)
- Maven - A build automation tool used primarily for Java projects. It helps manage project dependencies, the build lifecycle, and project documentation.
- Spotbug - A static analysis tool that finds bugs in Java programs by analyzing bytecode.

## Introduction
The Proof of Concept (POC) demonstrates the bug analysis process for the "salary-api" project from the OT-MICROSERVICES repository. This process focuses on identifying potential bugs and security vulnerabilities within the Java-based application 

## Steps 

### Install Java 17 and Maven
```
	sudo apt update
	sudo apt install openjdk-17-jdk
        sudo apt install maven
```
### Cloning Repo

```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
### Add the Spotbug dependency in pom.xml file


        <plugin>
          <groupId>com.github.spotbugs</groupId>
          <artifactId>spotbugs-maven-plugin</artifactId>
          <version>4.8.2.0</version>
          <dependencies>
            <dependency>
              <groupId>com.github.spotbugs</groupId>
              <artifactId>spotbugs</artifactId>
              <version>4.8.3</version>
            </dependency>
          </dependencies>
        </plugin>
