# Attendance API Technology Stack

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 06-09-24    | Version 1  | Komal Jaiswal   | 06-09-24       |

This README provides an overview of the technology stack used in our Attendance API project. Each section includes features, pros and cons, and relevant resources.

## Table of Contents
1. [Purpose](#1-purpose)
2. [PostgreSQL](#2-postgresql)
3. [Redis](#3-redis)
4. [Liquibase](#4-liquibase)
5. [Poetry](#5-poetry)
6. [Swagger UI](#6-swagger-ui)
7. [Conclusion](#7-conclusion)
8. [Refrence](#8-reference)
9. [Contact](#9-contact)


## 1. Purpose
We are preparing this document so that you can get the detailed information about **Attendance Microservices** which is designed in Python to manage Attendance information.

## 2. PostgreSQL

### Features:
- ACID-compliant relational database management system
- Supports complex queries and joins
- Offers robust data integrity and consistency
- Provides excellent support for concurrent operations
- Extensible with custom functions and data types

| Pros                                             | Cons                                                  |
|--------------------------------------------------|-------------------------------------------------------|
| High performance for complex queries             | Can be complex to set up and maintain                 |
| Strong data consistency and reliability          | May require more resources compared to lighter databases |
| Active community and extensive documentation     | Slower for simple read operations compared to some NoSQL solutions |
| Scalable for large datasets                      |                                                       |
| Supports JSON and other NoSQL-like features      |                                                       |

### Relevant Resources:
- [PostgreSQL Official Documentation](https://www.postgresql.org/docs/)
- [Why You Should Choose PostgreSQL for Your Next Project](https://www.postgresqltutorial.com/postgresql-getting-started/why-postgresql/)
- [PostgreSQL vs MySQL: Which is Better?](https://www.integrate.io/blog/postgresql-vs-mysql-which-one-is-better-for-your-use-case/)

## 3. Redis

### Features:
- In-memory data structure store
- Supports various data structures (strings, hashes, lists, sets, etc.)
- Provides pub/sub messaging system
- Offers data persistence options
- Includes built-in replication and cluster mode

| Pros                                         | Cons                                                 |
|----------------------------------------------|------------------------------------------------------|
| Extremely fast read/write operations         | Limited storage capacity (bound by RAM)              |
| Reduces database load by caching data        | Data can be lost if not configured for persistence   |
| Supports distributed locking and session management | Less suitable for complex queries compared to relational databases |
| Lightweight and easy to set up               |                                                      |
| Versatile for various use cases beyond caching |                                                      |

### Relevant Resources:
- [Redis Official Documentation](https://redis.io/documentation)
- [Redis: Beyond Simple Caching](https://redis.com/blog/redis-beyond-caching/)
- [Redis vs Memcached: Which One to Choose?](https://aws.amazon.com/elasticache/redis-vs-memcached/)

## 4. Liquibase

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

### Relevant Resources:
- [Liquibase Official Documentation](https://docs.liquibase.com/)
- [Getting Started with Liquibase: A Beginner's Guide](https://www.liquibase.org/get-started/quickstart)
- [Comparing Database Migration Tools: Liquibase vs Flyway](https://www.red-gate.com/blog/database-devops/liquibase-and-flyway-comparison)

## 5. Poetry

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

### Relevant Resources:
- [Poetry Official Documentation](https://python-poetry.org/docs/)
- [Why You Should Use Poetry for Python Dependency Management](https://realpython.com/dependency-management-python-poetry/)
- [Poetry vs Pipenv: Choosing the Right Python Dependency Management Tool](https://testdriven.io/blog/python-dependency-management/)


## 6. Swagger UI

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

![image](https://github.com/user-attachments/assets/35166bb1-44ed-4950-af79-4a4a32a964f9)

## 7.Conclusion

- **Robust Architecture**: The stack ensures high performance, reliability, and scalability, combining PostgreSQL for data persistence, Redis for caching, and Liquibase for managing database schema changes.
  
- **Streamlined Development**: Poetry simplifies Python dependency management, ensuring consistent environments and reproducible builds.
  
- **Balanced Language Choices**: Java provides stability for enterprise-level applications, while Python supports rapid development and integration.
  
- **Enhanced Developer Experience**: Swagger UI offers clear and interactive API documentation, improving testing and transparency.
  
- **Scalability and Future-Proofing**: The chosen technologies offer a solid foundation for future enhancements and scaling to accommodate growth.

- **Comprehensive Support**: Extensive documentation and active communities for each technology ensure ample support for continued development and troubleshooting.

## 8. Reference

| POC Name             | Description                                                | Link                                                                                                       |
|----------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Attendance API POC   | A detailed guide on setting up and running the Attendance API for proof of concept purposes. This document covers the steps required to configure, deploy, and test the API in a development environment. | [Setup and Run the App for POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Attendance/%20%20%20%09%20Setup%20and%20run%20the%20App%20for%20POC/readme.md) |


## 9. Contact Information
|Name|Email Address|
|:---:|:---:|
|Komal|komal.jaiswal.snaatak@mygurukulam.co|
