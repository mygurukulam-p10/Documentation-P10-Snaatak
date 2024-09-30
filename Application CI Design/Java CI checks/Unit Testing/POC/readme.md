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
