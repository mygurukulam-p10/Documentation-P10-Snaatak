# Employee API Detailed Document

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi       | 06-09-24    | Version 1  | Megha Tyagi   | 08-09-24       |


## About
In this document, we will provide a comprehensive overview of the dependencies associated with the Employee API and elucidate their roles and functionalities. The Employee API is a critical component of our microservices architecture, designed to handle all employee-related transactions efficiently. By understanding the dependencies and their interactions, we can gain insight into the operational aspects of the Employee API, ensuring robust and seamless integration within the overall system.

## Table of Contents
1. [Employee-api](#employee-rest-api)
2. [Architecture](#architecture)
3. [Pre-Requisites](#pre-requisites)
4. [Build-Dependencies](#build-dependencies)
5. [Golang](#golang)
6. [Swagger UI](#swagger-ui)
7. [Conclusion](#conclusion)
8. [Contact Information](#contact-information)
9. [References](#references)




## Employee Rest API 
The Employee REST API is a Golang-based microservice designed to handle all employee-related transactions within the OT-Microservices ecosystem. It is fully platform-independent, capable of running on any platform. The API features Gin for efficient web transactions, ScyllaDB as its primary database for robust data storage, and Redis for quick cache management. Additionally, it integrates Swagger for comprehensive API documentation and supports Prometheus metrics to monitor application health and performance.


### Architecture
![Employee_API Architecture drawio](https://github.com/user-attachments/assets/5b87b48d-8399-4ac7-8d49-361de4189828)

###  Pre-Requisites 
   - [Redis](#defination-of-redis)
<img width="47" alt="Redis-Logo-768x480" src="https://github.com/user-attachments/assets/3095ec95-88a7-42f4-921e-91960ae90a9b">

   
   - [ScyllaDb](#what-is-scylladb)
<img width="43" alt="Scylla_the_sea_monster" src="https://github.com/user-attachments/assets/29e536f3-e1b7-4dfe-a607-18f3ddf840ec">


     
#### Defination of Redis: 
"Redis (which stands for REmote DIctionary Server)is an open-source in-memory data structure store that also can be used as a database as well as caching. It supports almost all types of data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps. Redis also can be used for messaging systems used as pub/sub".  

##### Redis in Employee REST API
| Features | Description  |
|--------------------------|------------------------|
| Caching  | Temporarily stores frequently accessed data in memory to reduce the need for repeated database queries.|
| Data Storage| Acts as a high-speed, in-memory database for data accessed often but rarely changed.|
| Session Management| Manages user sessions and authentication tokens for quick accessibility and reduced database load.|
| Performance Improvement|Offloads read-heavy operations from ScyllaDB, improving overall system performance and scalability.|

   
#### Relevant Resources:
  -  **[Redis Official Documentation](https://redis.io/documentation)**
  -  **[Redis: Beyond Simple Caching](https://redis.com/blog/redis-beyond-caching/)**

  
 #### What is ScyllaDB:
ScyllaDB is a high-performance, distributed NoSQL database designed to handle large volumes of data with low latency. It is compatible with Apache Cassandra but offers improved speed and efficiency due to its advanced architecture.

##### ScyllaDB in Employee REST API

| Features | Description  |
|--------------------------|------------------------|
| Primary Database              | ScyllaDB serves as the primary database for storing employee-related data, such as profiles and transaction records.      |
| High Throughput                 | Designed to handle high write and read throughput, making it suitable for managing large datasets efficiently.               |
| Low Latency                 | Provides low-latency data access, ensuring quick response times for employee data retrieval and updates.                |
|Scalability                      | Offers horizontal scalability to accommodate growing amounts of data and increased load as the application scales.     |


#### Relevant Resources:
- **[ScyllaDB Homepage Documentation](https://www.scylladb.com/)**
- **[Stackoverflow](https://stackoverflow.com/questions/tagged/scylla?tab=Newest)**

### Build-Dependencies
 - [Migrations](#what-is-migrations)
 - [Jq](#what-is-jq)
     
 #### What is Migrations:
 Migrations refer to the process of managing and applying changes to a database schema over time. This typically involves creating, 
 modifying, or deleting database tables and columns to accommodate evolving application requirements. Migrations ensure that database 
 structures are updated in a controlled and consistent manner.


##### Migrations in Employee REST API

| Features | Description  |
|--------------------------|------------------------|
| Schema Evolution             | Migrations help manage changes to the database schema, such as adding new tables or columns for additional employee information or updating existing ones.     |
| Version Control                 | Track and apply changes to the database schema in a version-controlled manner, ensuring that updates are applied consistently across different environments.             |
| Data Integrity                |Ensure that schema changes do not disrupt existing data or application functionality, maintaining data integrity during updates.           |
|Automated Updates                    | OFacilitate automated application of schema changes, reducing manual intervention and minimizing the risk of errors.    |


#### Relevant Resources:
- **[Migrate:stackoverflow docs](https://stackoverflow.com/questions/tagged/migrate)**
- **[Migrate Github Docs](https://github.com/golang-migrate/migrate)**
- **[Migrate CLI](https://github.com/golang-migrate/migrate/blob/master/cmd/migrate/README.md)**
  

#### What is Jq
Jq is a powerful command-line tool used for parsing, filtering, and manipulating JSON data. It allows users to perform complex operations on JSON structures with a simple and expressive syntax, making it an invaluable tool for working with JSON data in scripts and command-line interfaces.

##### Jq in Employee REST API
| Features | Description  |
|--------------------------|------------------------|
|JSON Parsing|jq is used to parse JSON responses from the Employee API, extracting and processing specific data elements, such as employee records or API status messages|
|Data Filtering|Allows filtering of JSON data based on specific criteria, such as selecting employees based on their roles or statuses.|
|Data Transformation|Enables transformation of JSON data into different formats or structures for further processing or integration with other systems.|
|Debugging and Testing| Helps in debugging and testing API responses by allowing users to quickly inspect and validate JSON data returned by the Employee API.|

#### Relevant Resources:
- **[Jq](https://en.wikipedia.org/wiki/Jq_(programming_language))**
- **[Jq Digital Ocean Doc](https://www.digitalocean.com/community/tutorials/how-to-transform-json-data-with-jq)**



### Golang 
Go (Golang) is a statically typed, compiled programming language designed by Google, known for its simplicity, efficiency, and performance. It features built-in support for concurrency, making it ideal for building scalable and high-performance applications.

##### Golang in Employee REST API
| Features | Description  |
|--------------------------|------------------------|
|Microservice Architecture|Go is employed to build the Employee REST API as a microservice, allowing it to handle employee-related transactions independently within the OT-Microservices ecosystem.|
|Performance|Go’s efficient execution and low-latency performance contribute to the API's ability to handle high volumes of requests and data with minimal delay.|
|Concurrency| Utilizes Go’s concurrency model (goroutines and channels) to manage multiple simultaneous API requests and background tasks efficiently.|
|Scalability|Leverages Go’s performance features to ensure that the API can scale effectively as the number of employees or transactions grows.|
|Integration|Facilitates easy integration with other services and databases, such as ScyllaDB and Redis, through Go’s robust standard library and third-party packages.|

#### Relevant Resources:
- **[Go Official Documentation](https://go.dev/doc/))**
- **[Awesome Go](https://awesome-go.com/))**

### Swagger UI
Swagger UI is an open-source tool that provides a visual interface for interacting with and exploring RESTful APIs. It generates interactive documentation from OpenAPI specifications, enabling developers and users to easily understand, test, and validate API endpoints without needing to write code manually.

##### Swagger UI in Employee REST API
| Features | Description  |
|--------------------------|------------------------|
|API Documentation|Automatically generates and displays interactive documentation for the Employee API, detailing available endpoints, request parameters, and response formats.|
|Interactive Testing|Allows users and developers to test API endpoints directly from the browser interface, sending requests and viewing responses in real-time.|
|Improved Usability| Enhances the developer experience by providing a user-friendly interface for exploring and understanding the API’s functionality and behavior.|

#### Relevant Resources:
- **[Swagger UI Documentation](https://swagger.io/tools/swagger-ui/)**
- **[Getting Started with Swagger UI](https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/)**
- **[Best Practices for Using Swagger UI](https://swagger.io/resources/articles/best-practices-in-api-documentation/)**

#### Conclusion
The Employee REST API, built using Go, leverages various dependencies to ensure robust, scalable, and high-performance employee data management. Key dependencies like ScyllaDB provide efficient data storage, Redis enhances caching and quick data access, jq facilitates JSON manipulation, and Swagger UI offers clear, interactive API documentation. Together, these components work seamlessly to handle employee-related transactions effectively, providing a reliable solution within the OT-Microservices ecosystem.

#### Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address                       |
|--------------|-------------------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

#### References
| Links | Descriptions|
|-------|--------------|
|(https://redis.io/documentation)|Redis Official Documentation|
|(https://redis.com/blog/redis-beyond-caching/) | Redis: Beyond Simple Caching|
|https://www.scylladb.com/|ScyllaDB Homepage Documentation|
|https://stackoverflow.com/questions/tagged/scylla?tab=Newest|Stackoverflow|
|https://stackoverflow.com/questions/tagged/migrate|Migrate:stackoverflow docs|
|https://github.com/golang-migrate/migrate|Migrate Github Docs|
|https://github.com/golang-migrate/migrate/blob/master/cmd/migrate/README.md|Migrate CLI|
|https://en.wikipedia.org/wiki/Jq_(programming_language)|Jq|
|https://www.digitalocean.com/community/tutorials/how-to-transform-json-data-with-jq|Jq Digital Ocean Doc|
|https://go.dev/doc/|Go Official Documentation|
|https://awesome-go.com/|Awesome Go|
|https://swagger.io/tools/swagger-ui/|Swagger UI Documentation|
|https://swagger.io/docs/open-source-tools/swagger-ui/usage/installation/|Getting Started with Swagger UI|
|https://swagger.io/resources/articles/best-practices-in-api-documentation/|Best Practices for Using Swagger UI|
