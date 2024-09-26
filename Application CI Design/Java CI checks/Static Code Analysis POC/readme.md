## Proof of Concept (POC)

![java static](https://github.com/user-attachments/assets/16f124bd-65e8-45df-93ae-6611fd7617ed)

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
|  Vinay Bansal | 21-09-24    | Version 1  | Vinay Bansal     | 22-09-24       |



## Purpose
The purpose of this document is to provide a completed guide to step up Static Code.

## Table of Contents
- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [System Requirements](#system-requirements)
- [Step-by-step Installation](#step-by-step-installation)
- [Contact Information](#contact-information)
- [ References](#references)


## Introduction 
* This document will guide you through a Proof of Concept (PoC) for setting up static code. We will cover the necessary prerequisites, build time and run time dependency, as well as the how to resolve the error.


##  Pre-requisites

- Java Development Kit (JDK): Ensure you have JDK installed (preferably JDK 8 or higher).
- Apache Maven: Install Maven (version 3.x is recommended).
- Integrated Development Environment (IDE): An IDE like IntelliJ IDEA, Eclipse, or VSCode is recommended for easier project management and development.

## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Multi-Core              |
| RAM                      | 2 GB                    |
| Disk                     |5 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |

##  Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```

### Step 2: Change Directory
Change Directory to where your code is
```
cd salary-api
```

### Step 3: Maven Checkstyle Plugin
- To use Checkstyle with Maven, you can add the following configuration to your pom.xml file:
  ![image](https://github.com/user-attachments/assets/f7b64f67-5dd5-4c6b-82e8-bee5a88766be)


### Step 4: now we have to do Static Code Analysis using checkstyle
This command will execute the Checkstyle plugin to analyze the code based on the configured rules.

```
mvn checkstyle:check
```
![e3](https://github.com/user-attachments/assets/ec2ed6fa-93d2-4b01-b20c-4b5ad4d0be73)
![e1](https://github.com/user-attachments/assets/92864196-b869-4123-8f14-002492226735)

![e2](https://github.com/user-attachments/assets/ea380ede-2922-4c3c-acd0-4ef163b03eaf)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
**ADD package-info.java** here src/main/java/com/opstree/microservice/salary/service
```
/**
 * This package contains classes related to the salary management APIs.
 */
package com.opstree.microservice.salary.controller;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **remove 80 line characters**
- **Final File**
```
package com.opstree.microservice.salary.service;
import com.opstree.microservice.salary.model.Employee;
import com.opstree.microservice.salary.repository.SpringDataSalaryRepository;
import lombok.RequiredArgsConstructor;
import org.springframework.stereotype.Service;
import java.util.List;
import java.util.Optional;

/**
 * Service class for handling salary-related operations.
 */
@Service
@RequiredArgsConstructor
public class SpringDataSalaryService {

    /**
     * Repository for accessing salary data.
     */
    private final SpringDataSalaryRepository springDataSalaryRepository;

    /**
     * Saves a new employee salary record.
     * @param employee The employee object to be saved
     * @return The saved employee object
     */
    public Employee saveSalary(final Employee employee) {
        return springDataSalaryRepository.save(employee);
    }

    /**
     * Retrieves all employee salary records.
     * @return A list of all employee salary records
     */
    public List<Employee> getAllSalaries() {
        return springDataSalaryRepository.findAll();
    }

    /**
     * Retrieves an employee salary record by ID.
     * @param id The ID of the employee
     * @return An Optional containing the employee if found,
              or empty if not found.
     */
    public Optional<Employee> getSalaryById(final Long id) {
        return springDataSalaryRepository.findById(id);
    }

    // Additional methods can be added as needed...
}
```


![e4](https://github.com/user-attachments/assets/f1377a82-1729-446f-91ba-5e667a3a66be)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
#**ADD package-info.java** here src/main/java/com/opstree/microservice/salary
```
/**
 * This package contains service classes for managing salary information.
 */
package com.opstree.microservice.salary;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **Final File**
```
package com.opstree.microservice.salary;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.annotation.Bean;
import org.springframework.cache.annotation.EnableCaching;
import org.springframework.data.redis.cache.RedisCacheConfiguration;
import org.springframework.data.redis.cache.RedisCacheManager;
import org.springframework.data.redis.connection.RedisConnectionFactory;
import org.springframework.data.redis.core.RedisTemplate;
import org.springframework.data.redis.serializer.Jackson2JsonRedisSerializer;
import java.time.Duration;

/**
 * This class contains the main application for salary management.
 */
@SpringBootApplication
@EnableCaching
public final class SalaryApplication {

    /**
     * Configures the RedisTemplate for managing Redis operations.
     * @param connectionFactory the connection factory to be used
     * @return a configured RedisTemplate
     */
    @Bean
    public RedisTemplate<Object, Object> redisTemplate(
            final RedisConnectionFactory connectionFactory) {
        RedisTemplate<Object, Object> template = new RedisTemplate<>();
        template.setConnectionFactory(connectionFactory);
        Jackson2JsonRedisSerializer<Employee> serializer =
                new Jackson2JsonRedisSerializer<>(Employee.class);
        template.setDefaultSerializer(serializer);
        return template;
    }

    /**
     * Configures the RedisCacheManager for caching.
     * @param connectionFactory the connection factory to be used
     * @return a configured RedisCacheManager
     */
    @Bean
    public RedisCacheManager cacheManager(
            final RedisConnectionFactory connectionFactory) {
        RedisCacheConfiguration config = RedisCacheConfiguration
    .defaultCacheConfig()
                .prefixCacheNameWith(this.getClass().getPackageName() + ".")
                .entryTtl(Duration.ofSeconds(1))
                .disableCachingNullValues();
        return RedisCacheManager.builder(connectionFactory)
                .cacheDefaults(config)
                .build();
    }

    /**
     * The main method that starts the Spring Boot application.
     * @param args command line arguments
     */
    public static void main(final String[] args) {
        SpringApplication.run(SalaryApplication.class, args);
    }
}
```
![e9](https://github.com/user-attachments/assets/fc3480ea-7805-4430-b039-bce0f9970dc6)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
**ADD package-info.java** here src/main/java/com/opstree/microservice/salary/model
```
/**
 * This package contains model classes for the salary microservice.
 */
package com.opstree.microservice.salary.model;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **Final File**
```
package com.opstree.microservice.salary.model;
import java.io.Serializable;
import org.springframework.data.annotation.Id;
import org.springframework.data.cassandra.core.mapping.Column;
import org.springframework.data.cassandra.core.mapping.PrimaryKey;
import org.springframework.data.cassandra.core.mapping.Table;
import lombok.AllArgsConstructor;
import lombok.Builder;
import lombok.Data;
import lombok.NoArgsConstructor;
/**
 * Represents an employee's salary details.
 */
@Data
@AllArgsConstructor
@NoArgsConstructor
@Builder
@Table("employee_salary")
public class Employee implements Serializable {

    /**
     * The unique identifier of the employee.
     */
    @Id
    @PrimaryKey
    @Column("id")
    private String id;

    /**
     * The name of the employee.
     */
    @Column("name")
    private String name;

    /**
     * The salary of the employee.
     */
    @Column("salary")
    private Float salary;

    /**
     * The process date for the employee's salary.
     */
    @Column("process_date")
    private String processDate;

    /**
     * The status of the employee.
     */
    @Column("status")
    private String status;

    /**
     * Returns the unique identifier of the employee.
     *
     * @return the id of the employee
     */
    public String getId() {
        return id;
    }

    /**
     * Returns the name of the employee.
     *
     * @return the name of the employee
     */
    public String getName() {
        return name;
    }

    /**
     * Returns the salary of the employee.
     *
     * @return the salary of the employee
     */
    public Float getSalary() {
        return salary;
    }

    /**
     * Returns the process date for the employee's salary.
     *
     * @return the process date
     */
    public String getProcessDate() {
        return processDate;
    }

    /**
     * Returns the status of the employee.
     *
     * @return the status of the employee
     */
    public String getStatus() {
        return status;
    }
}
```

![e6](https://github.com/user-attachments/assets/7bc5f3a1-6f90-4e48-9c41-416287bd59ac)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
**ADD package-info.java** here src/main/java/com/opstree/microservice/salary/model
```
/**
 * This package contains service classes for managing salary information.
 */
package com.opstree.microservice.salary;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **Final File**
```
package com.opstree.microservice.salary.model;

/**
 * This package contains model classes for the salary microservice.
 */

public class Message {
    /**
     * The message content.
     */
    private String message;

    /**
     * Constructs a Message with the specified content.
     *
     * @param paramMessage the content of the message
     */
    public Message(final String paramMessage) {
        this.message = paramMessage;
    }
}
```





![e5](https://github.com/user-attachments/assets/10f5bd58-deca-4341-8c70-1989337d7f45)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
**ADD package-info.java** here src/main/java/com/opstree/microservice/salary/repository
```
/**
 * This package contains repositories for managing employee salary data.
 */
package com.opstree.microservice.salary.repository;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **remove 80 line characters**
- **Final File**
```
package com.opstree.microservice.salary.repository;

import com.opstree.microservice.salary.model.Employee;
import java.util.UUID;
import org.springframework.data.cassandra.repository.CassandraRepository;
import org.springframework.data.cassandra.repository.Query;

/**
 * This interface contains repositories for managing employee salary data.
 */
public interface EmployeeRepository
        extends CassandraRepository<Employee, UUID> {

    /**
     * Finds an employee by their ID as a string.
     *
     * @param id the ID of the employee as a string
     * @return the Employee object if found, otherwise null
     */
    @Query("SELECT * FROM employee_salary WHERE id = ?0")
    Employee findByIdAsString(String id);
}
```
![e10](https://github.com/user-attachments/assets/23bb63f8-92b3-40e4-8f2a-b456d4becb61)
- this documentation helps other developers understand the role of the package within the larger application, improving code readability and maintainability.
**ADD package-info.java** here src/main/java/com/opstree/microservice/salary/contollers
```
/**
 * This package contains classes related to the salary management APIs.
 */
package com.opstree.microservice.salary.controller;
```

- **remove unused import**
- **ADD Javadoc Coment**
- **Final File**
```
package com.opstree.microservice.salary.service;
import com.opstree.microservice.salary.model.Employee;
import com.opstree.microservice.salary.repository.SpringDataSalaryRepository;
import lombok.RequiredArgsConstructor;
import org.springframework.stereotype.Service;
import java.util.List;
import java.util.Optional;

/**
 * Service class for handling salary-related operations.
 */
@Service
@RequiredArgsConstructor
public class SpringDataSalaryService {

    /**
     * Repository for accessing salary data.
     */
    private final SpringDataSalaryRepository springDataSalaryRepository;

    /**
     * Saves a new employee salary record.
     * @param employee The employee object to be saved
     * @return The saved employee object
     */
    public Employee saveSalary(final Employee employee) {
        return springDataSalaryRepository.save(employee);
    }

    /**
     * Retrieves all employee salary records.
     * @return A list of all employee salary records
     */
    public List<Employee> getAllSalaries() {
        return springDataSalaryRepository.findAll();
    }

    /**
     * Retrieves an employee salary record by ID.
     * @param id The ID of the employee
     * @return An Optional containing the employee if found,
              or empty if not found.
     */
    public Optional<Employee> getSalaryById(final Long id) {
        return springDataSalaryRepository.findById(id);
    }

    // Additional methods can be added as needed...
}
```


![ssucces](https://github.com/user-attachments/assets/4e12bbb5-0aed-4246-8234-3cec4d8d8687)





## Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## 📚References
| Links | Descriptions|
|------|---------------------|
| Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/Java%20CI%20checks/Static%20Code%20Analysis%20Doc/readme.md|
