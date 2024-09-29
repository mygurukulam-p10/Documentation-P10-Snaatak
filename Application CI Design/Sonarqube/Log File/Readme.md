# SonarQube Logging Documentation

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 23-09-24    | version 1  | Amit Nagar      | 24-09-24       |

## Table of Contents

1. [Introduction](#Introduction)
2. [Types of Logs](#types-of-logs)
3. [Log Levels](#log-levels)
4. [Log Configuration](#log-configuration)
5. [Conclusion](#conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#references)


## Introduction
The purpose of this document is to provide a detailed overview of the logging system in SonarQube, including the types of logs generated, the significance of different log levels, and how to configure log settings. By outlining these elements, the documentation aims to assist administrators and users in understanding how to monitor and troubleshoot SonarQube effectively.



## Types of Logs

| Log File                     | Description                                                                           |
|------------------------------|---------------------------------------------------------------------------------------|
| **`access.log`**            | Logs all HTTP access requests to the SonarQube server.                               |
| **`ce.log`**                | Logs background tasks related to code analysis and project processing.               |
| **`deprecation.log`**       | Logs warnings about deprecated features and their usage.                             |
| **`es.log`**                | Ops information from the Elasticsearch service, such as startup and health status.  |
| **`sonar.log`**             | General log for the main SonarQube process, including startup and shutdown info.   |
| **`web.log`**               | Logs HTTP requests and responses handled by the SonarQube web server.               |


## Log Levels
SonarQube supports several log levels to classify the importance of log messages:

| Log Level | Description                                          |
|-----------|------------------------------------------------------|
| TRACE     | Detailed information used for debugging.             |
| DEBUG     | Information useful for developers, including technical details. |
| INFO      | General information about the system's operations.   |
| WARN      | Indicates potential issues or warnings.              |
| ERROR     | Indicates an error that occurred in the application.  |
| FATAL     | Critical errors that may cause the system to crash.  |

## Log Configuration
SonarQube allows you to configure logging settings through the `sonar.properties` file. You can set log levels for different components by modifying the following properties:

```properties
# Example configuration
sonar.log.level.web=INFO
sonar.log.level.ce=DEBUG
sonar.log.level.es=DEBUG
sonar.log.level.db=INFO
```

### Conclusion

SonarQube provides a detailed logging system crucial for monitoring platform behavior, troubleshooting issues, and ensuring efficient performance. Logs such as **Web**, **Compute Engine**, **Elasticsearch**, and **Access** help administrators manage and optimize the platform effectively.

## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


### References

| Reference Title                          | Link                                                                                          |
|------------------------------------------|-----------------------------------------------------------------------------------------------|
| SonarQube Log Management                 | [SonarQube Log Management](https://docs.sonarqube.org/latest/instance-administration/log-management/) |
| Understanding SonarQube Logs             | [Understanding SonarQube Logs](https://community.sonarsource.com/t/understanding-sonarqube-logs/2023) |

