# Fullstack Documentation

|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|17-09-2024|1|Aayush Gaur| Full Stack Documentation | 


### full stack image

## Introduction

Full Stack Development is the process of creating a complete web application that includes front-end, back-end, and database management. 

**Front-End**: This is what users see and interact with on the website. It focuses on the look and feel, making sure the site is easy to use and looks good.

**Back-End**: This is the behind-the-scenes part. It handles the server, the logic of the application, and ensures everything works correctly. It also manages security and data processing.

**Database Management**: This part is about storing and organizing all the data the application needs. It makes sure data can be easily accessed and managed.

## Overall Component Architecture Flow

Front-end development focuses on the part of a web application that users see and interact with. It's all about designing how the app looks (user interface) and how it feels to use (user experience). Front-end developers use languages like HTML, CSS, and JavaScript to build this visual part of the website, making sure it's easy to use and works smoothly.

Pre-Requisites
The frontend application have dependencies on other REST API of OT-Microservices.

#image

To run the application successfully, These things should be configured
For Refrence Links Below
* [Documentation](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Frontend/Detailed%20documentation/Readme.md)
* [POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Frontend/Setup%20and%20run%20the%20App%20for%20POC%20/Readme.md) 
* [Employee API](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Employee/Setup%20and%20run%20the%20App%20for%20POC%20/Readme.md)
* [Attendance API](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Attendance/%20%20%20%09%20Setup%20and%20run%20the%20App%20for%20POC/readme.md)
* [Salary API](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Salary/Setup%20and%20POC/README.md)

### Backend Management

#### 1 .Employee-API
The Employee REST API is a Go-based microservice that manages all employee-related transactions within the OT-Microservices stack. It is fully platform-independent, meaning it can run on any type of operating system or platform.

#image
Create this same as above.
Pre-Requisites
For running the application, we need following things configured:
For Refrence Links Below
* [Documentation](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Employee/Detailed%20Document/Readme.md) 
* [POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Employee/Setup%20and%20run%20the%20App%20for%20POC%20/Readme.md) 
* [ScyllaDB](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Scylla%20DB/Run%20ScyllaDB%20locally%20and%20POC/README.md)
* [Redis](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Setup%20and%20run%20App%20for%20POC/README.md)

#### 2. The Salary API
The Salary API is a Java-based microservice that handles all salary-related transactions and records within the OT-Microservices stack. It is platform-independent, meaning it can run on various operating systems. However, to run this application, a Java Runtime Environment (JRE) is required.

#image
We only need maven as build tool, but for running the application following things are required
For Refrence Link are below 
* [Documentation](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Salary/Detailed%20Document/README.md)
* [POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Salary/Setup%20and%20POC/README.md)
* [ScyllaDB](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Scylla%20DB/Run%20ScyllaDB%20locally%20and%20POC/README.md)
* [Redis](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Setup%20and%20run%20App%20for%20POC/README.md)
* [Java](https://maven.apache.org/)

#### 3 .The Attendance api
The Attendance REST API is a Python-based microservice that manages all attendance-related transactions within the OT-Microservices stack. This application is cross-platform, meaning it can run on different operating systems. The only requirement to run it is the Python runtime environment.
#image
To run the application successfully, we need these things configured

PostgresSQL as a primary database for storing all the attendance records
Redis as cache management middleware for storing all API response
Below Have Refrence Links in detail
* [Documentation](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Attendance/Detailed%20Document/README.md) 
* [POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Attendance/%20%20%20%09%20Setup%20and%20run%20the%20App%20for%20POC/readme.md) 
* [PostgresSQL](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/PostgreSQL/Setup%20and%20run%20the%20PostgreSQL%20for%20POC/Readme.md) 
* [Redis](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Setup%20and%20run%20App%20for%20POC/README.md)
* [Poetry](https://www.digitalocean.com/community/tutorials/how-to-install-poetry-to-manage-python-dependencies-on-ubuntu-22-04)
* [Liquibase](https://docs.liquibase.com/start/install/liquibase-linux-debian-ubuntu.html)

### Database Management

Database management is responsible for storing, accessing, and managing data for an application. It involves tasks such as creating databases, maintaining their performance, and optimizing them to ensure efficient data handling.
For Refrence Links Below
* [ScyllaDB](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Scylla%20DB/Run%20ScyllaDB%20locally%20and%20POC/README.md)
  
* [PostgresSQL](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/PostgreSQL/Detailed%20Document/README.md)
  
* [Redis](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Detailed%20Document/README.md)

