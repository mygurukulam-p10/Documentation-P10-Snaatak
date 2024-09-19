# Attendance API - Detailed Documentation

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 06-09-24    | Version 1  | Komal Jaiswal   | 19-09-24       |

This README provides an overview of the technology stack used in our Attendance API project. Each section includes features, pros and cons, and relevant resources.

## Table of Contents
1. [Purpose](#1-purpose)
2. [Flow Diagram of Attendance API](#2-flow-diagram-of-attendance-api)
3. [PostgreSQL](#3-postgresql)
4. [Redis](#4-redis)
5. [Liquibase](#5-liquibase)
6. [Poetry](#6-poetry)
7. [Swagger UI](#7-swagger-ui)  
8. [Conclusion](#8-conclusion)
9. [Reference](#9-reference)
10. [Contact](#10-contact)


## 1. Purpose
We are preparing this document so that you can get the detailed information about **Attendance Microservices** which is designed in Python to manage Attendance information.

### 2. Flow Diagram of Attendance API 

![image](https://github.com/user-attachments/assets/703c52a8-41a3-4b88-b621-2d467393fb10)

| Step                    | Description                                                                                       |
|-------------------------|---------------------------------------------------------------------------------------------------|
| **User Interaction**     | The user sends an HTTP request to the **Frontend Web** interface.                                  |
| **Frontend Processing**  | The **Frontend Web** communicates with the **Attendance API** to retrieve or process attendance data. |
| **Redis Caching**        | The **Attendance API** interacts with **Redis** to handle caching for quick data retrieval, optimizing performance. |
| **Database Persistence** | **PostgreSQL** is used as the primary database where the attendance records are stored permanently. |
| **Response**             | After processing, the **Frontend Web** sends the response back to the user with the required information. |

**Note**: This flow optimizes performance by utilizing Redis as a caching layer before accessing the main PostgreSQL database.

## 3. PostgreSQL

### Features:
- ACID-compliant relational database management system
- Supports complex queries and joins
- Offers robust data integrity and consistency
- Provides excellent support for concurrent operations
- Extensible with custom functions and data types


### Relevant Resources:
- [PostgreSQL Official Documentation](https://github.com/mygurukulam-p10/Documention/tree/main/OT%20MS%20Understanding/PostgreSQL)

## 4. Redis

### Features:
- In-memory data structure store
- Supports various data structures (strings, hashes, lists, sets, etc.)
- Provides pub/sub messaging system
- Offers data persistence options
- Includes built-in replication and cluster mode

### Relevant Resources:
- [Redis Official Documentation](https://github.com/mygurukulam-p10/Documention/tree/main/OT%20MS%20Understanding/Redis)

## 5. Liquibase

In Attendance Application We will use Liquibase for schema Management and Rollback to the previous version if required.

### Features:
- Database-independent library for tracking, managing, and applying database schema changes
- Supports multiple formats for change logs (XML, YAML, JSON, SQL)
- Provides rollback capabilities
- Offers diff capabilities to compare database schemas
- Integrates with various build and CI/CD tools

| Pros                                           | Cons                                                |
|------------------------------------------------|-----------------------------------------------------|
| Database agnostic, supports a wide range of databases | Can have a steeper learning curve compared to simpler tools |
| Provides a clear history of database changes   | May add complexity to smaller projects              |
| Enables easier collaboration among team members | Performance can be an issue with very large change sets |
| Supports complex migration scenarios           |                                                     |
| Integrates well with Java ecosystem            |                                                     |

![image](https://github.com/user-attachments/assets/7a64e8b6-0790-4278-868e-02c67e30c8ea)

Reference

[Liquibase Documentation](https://github.com/mygurukulam-p10/Documention/tree/main/VCS%20Design%20%2B%20POC/Database%20Release%20Management%20/POC%20on%20Liquibase)

### Relevant Resources:
- [Liquibase Official Documentation](https://docs.liquibase.com/)
- [Getting Started with Liquibase: A Beginner's Guide](https://www.liquibase.org/get-started/quickstart)
- [Comparing Database Migration Tools: Liquibase vs Flyway](https://www.red-gate.com/blog/database-devops/liquibase-and-flyway-comparison)

## 6. Poetry

Poetry is used for environment management in attendance API , For different dependencies installation in an environment.

### Features:
- Dependency management and packaging tool for Python
- Provides virtual environment management
- Offers a lockfile for reproducible builds
- Supports building and publishing packages
- Integrates with pyproject.toml for project metadata

| Pros                                           | Cons                                             |
|------------------------------------------------|--------------------------------------------------|
| Simplifies Python project setup and dependency management | May have a learning curve for developers used to pip and requirements.txt |
| Ensures consistent environments across development and production | Some compatibility issues with older Python versions |
| Improves project reproducibility               | Limited support in some CI/CD platforms compared to pip |
| Offers an intuitive CLI for managing dependencies |                                                 |

![image](https://github.com/user-attachments/assets/9966e874-e404-474d-a480-fb5f606ceb30)

### Relevant Resources:
- [Poetry Official Documentation](https://python-poetry.org/docs/)
- [Why You Should Use Poetry for Python Dependency Management](https://realpython.com/dependency-management-python-poetry/)
- [Poetry vs Pipenv: Choosing the Right Python Dependency Management Tool](https://testdriven.io/blog/python-dependency-management/)


## 7. Swagger UI

It is used for the Visualization of Data we are storing and getting.

### Features:
- Interactive API documentation and testing tool
- Automatically generates documentation from OpenAPI specifications
- Provides a user-friendly interface for exploring API endpoints
- Supports both RESTful and SOAP web services
- Customizable with themes and plugins

| Pros                                         | Cons                                                  |
|----------------------------------------------|-------------------------------------------------------|
| Easy to set up and integrate with Python-based APIs | Can add extra steps to the API development workflow    |
| Improves developer experience with interactive API exploration | May expose internal API details if not configured properly |
| Supports live testing of API endpoints       | Limited styling options compared to custom documentation solutions |
| Automatically updates with API changes       |                                                       |

### Relevant Resources:
- [Swagger UI Documentation](https://swagger.io/tools/swagger-ui/)
- [Getting Started with Swagger UI](https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/)
- [Best Practices for Using Swagger UI](https://swagger.io/resources/articles/best-practices-in-api-documentation/)


## 8.Conclusion

| Feature                | Description                                                                   |
|------------------------|-------------------------------------------------------------------------------|
| **Robust Stack**       | Combines PostgreSQL, Redis, and Liquibase for performance and scalability.    |
| **Efficient Development** | Poetry manages dependencies; Java and Python offer stability and speed.        |
| **User-Friendly**      | Swagger UI enhances API clarity and testing.                                  |
| **Scalable**           | Technologies are suited for future growth.                                    |
| **Great Support**      | Strong documentation and communities ensure reliable assistance.              |


## 9. Reference

| POC Name             | Description                                                | Link                                                                                                       |
|----------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Attendance API POC   | A detailed guide on setting up and running the Attendance API for proof of concept purposes. This document covers the steps required to configure, deploy, and test the API in a development environment. | [Setup and Run the App for POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Attendance/%20%20%20%09%20Setup%20and%20run%20the%20App%20for%20POC/readme.md) |


## 10. Contact Information
|Name|Email Address|
|:---:|:---:|
|Komal|komal.jaiswal.snaatak@mygurukulam.co|
