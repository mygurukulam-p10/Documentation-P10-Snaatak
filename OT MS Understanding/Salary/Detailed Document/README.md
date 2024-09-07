# SALARY API  

|CREATED/UPDATED |VERSION|AUTHOR|COMMENT|
|--------|-----------|-------|---------|
|06-09-2024|1|Aayush Gaur|Documentation on Salary API| 


## Table of Content 
- [Purpose](#Purpose)
- [Pre-reqisites](#Pre-requisites)
- [System Requirement](#System-Requirement)
- [Build-Time Dependency](#Build-Time-Dependency)
- [Run-Time Dependency](#Run-Time-Dependency)
- [Architecture ](#Architecture)
- [ Data Flow ](#Data Flow )
- [ Setting Up the Environment](#Setting-Up-the-Environment)
- [Building and Running the Salary API](#Bilding-and-Running-the-SalaryAPI)
- [Conclusion](#Conclusion)
- [ Endpoints ](#Endpoints )
- [ References ](#References ) 
- [Contact Information ](#Contact-Information )
     
## Purpose 
The Salary API project is a Java-based microservice designed to manage and process employee salary data. This Application is must be independent and can be run on multiple operating system. JAVA RUNTIME would be required to run this application.


## Pre-requisites
The Salary API application have some database, cache manager and package dependencies. Ensure you have the following on your system :
* [ScyllaDB](https://www.scylladb.com/)
* [Redis](https://redis.io/)
* [Maven](https://maven.apache.org/)
  
## System Requirements 
|Hardware Specification |Minimum Recommendation|
|:-----------------------:|:----------------------:|
|Processor              | Dual-core            |
|RAM                    | 4GB                  |
|Disk                   | 20GB                 |
|OS                     |Ubuntu(22.04)         |

## Build-Time Dependency
| Name | Version | Description |
|:-----:|:------:|:------------:|
|Maven|3.+|It simplifies the management of build procedures, project documentation, and project dependencies.|

## Run-Time Dependency
|Name  | Version | Description |
|:------:|:-------:|:----------:|
|JAVA|  17| Running the built Java application is required.|


## Architecture 

![Screenshot from 2024-09-07 15-24-03](https://github.com/user-attachments/assets/346eecc7-7b08-4ba1-b5f1-c07b9732a23e)


## Data Flow 

#### Salary API Request:
* When the Salary API needs data, it first checks the Redis cache (a fast, in-memory data store) to see if the data is already there.
* If the data is found in Redis (cache hit), it is immediately returned to the API without needing to access the database.

#### Cache Miss Handling:
* If the data is not found in Redis (cache miss), the API then looks for the data in ScyllaDB (a distributed database).
* If the data is found in ScyllaDB, it is returned to the API.

#### Updating the Cache:
* After retrieving the data from ScyllaDB, the system stores it in Redis for future requests, which speeds up subsequent access by avoiding the need to query the database again.

#### Migrations:
* Any changes to the database schema (like adding a new table or column) are handled by a migration process, which updates ScyllaDB accordingly.

## Setting Up the Environment
**ScyllaDB**

```ScyllaDB is a high-performance, NoSQL database designed for low-latency and high-throughput applications. It is compatible with Apache Cassandra, ScyllaDB can handle large amounts of data with minimal operational overhead, making it ideal for real-time big data applications, It is used in the salary-api to handle large amounts of data efficiently, offering scalability and performance benefits.```

To install ScyllaDB, execute the following commands:
```
sudo mkdir -p /etc/apt/keyrings
sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list

sudo apt-get update
sudo apt-get install scylla
sudo scylla_setup
sudo systemctl start scylla-server
```
**Redis**

``` Redis (Remote Dictionary Server) is an in-memory data structure store used as a database, cache, and message broker. It supports various data types such as strings, lists, sets, hashes, and more. Redis is known for its speed, low latency, and high throughput, making it ideal for real-time applications like caching, session management, and real-time analytics, In salary-api, Redis might be used to improve performance by caching data or managing temporary states.```


To install Redis, use the following commands:
```
 sudo apt install redis-server
 sudo systemctl start redis-server
 sudo systemctl status redis-server
 redis-cli
```

### Required Libraries
**Install JDK 17**

``` This stands for Java Development Kit 17, which is a version of the JDK used to develop Java applications. JDK 17 is an LTS (Long-Term Support) release, meaning it will receive updates and support for a longer period. It includes new features and performance improvements over previous versions, making it suitable for building modern Java applications.```

To install JDK 17, run:
```
sudo apt install openjdk-17-jdk
```

**Install Maven**

``` Maven is a powerful build automation and project management tool primarily used for Java projects. It simplifies the process of managing project dependencies, compiling code, running tests, and packaging applications. ```

To install Maven, execute:
```
sudo apt install maven
```
**Install Migrate**

```  In the context of salary-api, it could involve migrating data between databases or upgrading the application to use newer technologies or versions. ```

To install Migrate, use the following commands:
```
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz -o migrate.tar.gz
tar -xvzf migrate.tar.gz
sudo mv migrate /usr/local/bin/
sudo chmod +x /usr/local/bin/migrate
```
## Building and Running the Salary API
### 1. For building the Salary API application, we can use make commands

```
make build
```
### 2. To automate the process of applying database migrations in a project, Use this command
```
make run-migrations
```

### Running the Java Application
To run the Java application, navigate to the project directory and use the following command:
```
java -jar target/salary-api.jar
```


## Conclusion
Following these steps, you will set up the necessary environment for the Salary API, build the project, and run the application. Ensure that all commands are executed in the correct order and in a terminal with sufficient privileges.
Other Endpoint are below 

## Endpoints 
|Endpoint|Method|Description|
|--------|-------|----------|
|/api/v1/salary/create/record|POST |Data creation endpoint which accepts certain JSON body to add salary inf|
|/api/v1/salary/search|GET|Endpoint for searching data information using the params in the URL|    
|/api/v1/salary/search/all|GET|Endpoint for searching all information across the system|
|/actuator/prometheus|GET|Application healthcheck and performance metrics are available on this endpoint|
|/actuator/health|GET|Endpoint for providing shallow healthcheck information about application|


## References 
|links | Description |
|-------|------------|
|https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/install-redis-on-linux/|For Redis |
|https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html| For Scylladb|
|https://github.com/OT-MICROSERVICES/salary-api|For understanding the workflow of salary api|

## Contact Information 
|Name|Email Address|
|:---:|:---:|
|Aayush|aayush.gaur.snaatak@mygurukulam.co|
