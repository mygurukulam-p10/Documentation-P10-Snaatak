# Proof of Concept (POC) for Java Unit Testing

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 28-09-2024         | 1.0  | Aayush Gaur  |     POC: Unit Testing         |

## Introduction
Unit testing in Java is an essential practice for ensuring the correctness and functionality of individual code units. By isolating and testing these components, developers can improve code reliability and reduce the likelihood of errors. In this document, we will outline the steps for setting up and executing unit tests using the JUnit framework in a typical Java project.

## Testing Framework
Java unit testing is facilitated by various testing frameworks, with JUnit being one of the most widely adopted. JUnit provides a structured way to write, organize, and execute tests.

Overview
The salary microservice has pre-existing unit test cases authored by the developer, which are located in the following directory path:

```
src/test/java/com/opstree/microservice/salary
```


## Prerequisites
- Java Version 17 (as specified in pom.xml)
- Maven: Maven simplifies dependency management and project build processes, including testing.
- JUnit: A necessary library for executing the unit tests.

## Steps to perform

### Cloning the Java Application
To begin, clone the salary-api repository from GitHub into your local directory:
```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
## Install Java 17 and Maven
Since the salary codebase relies on Java 17, it is essential to install the correct version of Java and Maven for managing project dependencies.
```
sudo apt update
sudo apt install openjdk-17-jdk
sudo apt install maven
```

## Add the JUnit Dependency to ```pom.xml```
Ensure that the JUnit dependency is added to your ```pom.xml``` file:
```
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
    <scope>test</scope>
</dependency>
```
![Screenshot from 2024-09-30 11-11-44](https://github.com/user-attachments/assets/eed82ec6-fc50-4982-8789-868f90016385)

## Add Maven Dependency in ```pom.xml```
Add the Maven compiler plugin to your ```pom.xml``` file for compiling your Java project:
```
<dependency>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <version>3.11.0</version>
    <type>maven-plugin</type>
</dependency>
```


