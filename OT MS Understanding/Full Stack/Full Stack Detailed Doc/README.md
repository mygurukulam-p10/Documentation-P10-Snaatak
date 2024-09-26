# Fullstack Documentation

|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|17-09-2024|1|Aayush Gaur| Full Stack Documentation | 


### full stack image
![image](https://github.com/user-attachments/assets/8a3c6bfe-2846-4ba2-9dcb-d8935a3ef2e8)

## Introduction

Full Stack Development is the process of creating a complete web application that includes front-end, back-end, and database management. 

**Front-End**: This is what users see and interact with on the website. It focuses on the look and feel, making sure the site is easy to use and looks good.

**Back-End**: This is the behind-the-scenes part. It handles the server, the logic of the application, and ensures everything works correctly. It also manages security and data processing.

**Database Management**: This part is about storing and organizing all the data the application needs. It makes sure data can be easily accessed and managed.


## Overall Component Architecture Flow

### Frontend Flow

Front-end development focuses on the part of a web application that users see and interact with. It's all about designing how the app looks (user interface) and how it feels to use (user experience). Front-end developers use languages like HTML, CSS, and JavaScript to build this visual part of the website, making sure it's easy to use and works smoothly.

Pre-Requisites
The frontend application have dependencies on other REST API of OT-Microservices.

![367527759-b0c15c34-cf98-4708-be93-b1c9b3df05cf](https://github.com/user-attachments/assets/a489b959-b1fc-42e3-b7dd-62ffb59855df)

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

![Screenshot from 2024-09-19 12-45-13](https://github.com/user-attachments/assets/fede28a3-554d-44d2-a05d-ea48e80f3cf4)

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

![salry](https://github.com/user-attachments/assets/11965775-905e-4fa3-85eb-736435f4fc8e)

We only need maven as build tool, but for running the application following things are required
For Refrence Link are below 
* [Documentation](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Salary/Detailed%20Document/README.md)
* [POC](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Salary/Setup%20and%20POC/README.md)
* [ScyllaDB](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Scylla%20DB/Run%20ScyllaDB%20locally%20and%20POC/README.md)
* [Redis](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Setup%20and%20run%20App%20for%20POC/README.md)
* [Java](https://maven.apache.org/)

#### 3 .The Attendance api
The Attendance REST API is a Python-based microservice that manages all attendance-related transactions within the OT-Microservices stack. This application is cross-platform, meaning it can run on different operating systems. The only requirement to run it is the Python runtime environment.

![attendance](https://github.com/user-attachments/assets/ee552d33-f594-4580-8d6a-ef4736bf262e)

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

### User Flow
![Alt text](https://prepbytes-misc-images.s3.ap-south-1.amazonaws.com/assets/1673592711181-What%20is%20Full%20Stack%20Development1.png)
---

| **User Registration Flow* |                
|---------------|
| User submits the registration form. |     
| Frontend validates the input. |                                     
| The request is sent to the backend. |                       
| The backend processes the registration and stores the data in the database. |        
| A response is sent back to the frontend. |                                      
---

| **User Login Flow** |                                                  
|---------------------|                                      
| User submits the login form. |                                       
| Frontend validates the input. |                                           
| The request is sent to the backend. |                                     
| The backend authenticates the user. |                                    
| A response is sent back to the frontend with a token. |            
---

| **Data Processing Flow** |                                                                                        
|---------------------------|-
| Data is submitted from the frontend. |                                                               
| The backend processes the data. |                                                                         
| Data is validated and transformed. |                                                                
| Processed data is stored in the database. |                                                           
| Confirmation is sent back to the frontend. |                                                       
---
### Conclusion
This document gives a clear overview of full-stack development for the OT-MICROSERVICES project. It explains how the front end and back end work together and shares important practices for building strong and easy-to-maintain applications. 

## Contact Information

| Name          | Email Address                          | 
| ------------- |:--------------------------------------:|
| Aayush      | aayush.gaur.snaatak@mygurukulam.co |

## Refrences 

| Links          |
| ------------- |
|    https://github.com/OT-MICROSERVICES  | 
|     | 

