# Golang CI Checks - Static Code Analysis - Proof of Concept 🚀

| Author | Created on | Version | Last updated by | Last edited on |
|--------|------------|---------|----------------|----------------|
| Komal Jaiswal | 25-09-2024 | 1.0 | Komal Jaiswal  | 26-09-2024 |

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
3. [Step-by-step installation](#step-by-step-installation)
4. [References](#references)
5. [Contact Information](#contact-information)

## Purpose 🎯
The purpose of this documentation is to provide a comprehensive overview of static code analysis in Golang using Golangci-lint. It aims to guide developers and teams in integrating Golangci-lint into their CI/CD workflows, emphasizing best practices, benefits, and practical implementation steps.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | single-core              |
| RAM                     | 1GB                    |
| Disk                    | 10GB                   |
| OS                      | Ubuntu 22.04           |

### Dependencies

| Name     | Version | Description                              |
|----------|---------|------------------------------------------|
| Golang   | 1.18.1  | Programming language for the application |


## Step-by-step installation

To demonstrate the capabilities of Golangci-lint, here’s a simple setup guide. We will be using our Microservice ```Employee-API```

1. **Clone the Repository**

```
https://github.com/OT-MICROSERVICES/employee-api.git
```

2. **Install Golangci-lint**:

```
sudo snap install golangci-lint --classic
```


![image](https://github.com/user-attachments/assets/87fb9498-be1b-40cd-a35f-ae3a52b4b66c)


3. **Go to your Application Directory, In my case (Employee-API)**:

```
cd employee-api/
```


![image](https://github.com/user-attachments/assets/7e012efe-10d5-4d1c-b8ec-062060c46374)
 
4. **Run Golangci-lint on Employee-API**:

1. To Run it on Single file. Use command below

```
golangci-lint run < File name with extension .go>
```

Example 
```
golangci-lint run main.go

```
![image](https://github.com/user-attachments/assets/7b90ff4b-1942-41e9-89bc-b448b7accfa0)

2. To run it on overall files use command below.

```
golangci-lint run 

```

![image](https://github.com/user-attachments/assets/8ba89f07-6075-43f2-bff6-df06e626d2d9)

Note :- This is checking error in each file with extension ```.go ``` .

| **File**                         | **Line**  | **Issue**                                                                | **Description**                                                       |
|-----------------------------------|-----------|--------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `main.go`                         | 47:12     | Error return value not checked (errcheck)                                | `router.Run(":8080")` – Error is not handled.                         |
| `api/api.go`                      | 71:16     | Error return value not checked (errcheck)                                | `json.Unmarshal(jsonData, &designationResponse)` – Error is not handled. |
| `api/api.go`                      | 95:17     | Error return value not checked (errcheck)                                | `json.Unmarshal([]byte(redisData), &locationResponse)` – Error is not handled. |
| `api/api.go`                      | 128:16    | Error return value not checked (errcheck)                                | `json.Unmarshal(jsonData, &locationResponse)` – Error is not handled. |
| `api/health_test.go`              | 82:31     | Error return value not checked (errcheck)                                | `mockRedisClient.Ping(ctx).Err()` – Error is not handled.             |
| `api/api.go`                      | 97:3      | Redundant return statement (gosimple)                                    | The `return` statement is unnecessary and can be removed.             |
| `api/api.go`                      | 130:2     | Redundant return statement (gosimple)                                    | Same as above.                                                        |
| `api/api.go`                      | 235:3     | Loop unconditionally terminated (staticcheck)                            | The loop is always terminated by a `return`, making the loop useless. |
| `client/scylladb_test.go`         | 40:24     | Error return value not checked (errcheck)                                | `gocql.CreateSessionMock()` – Error is not handled.                   |
| `config/viper_test.go`            | 36:19     | Error return value not checked (errcheck)                                | `viperReadInConfig()` – Error is not handled.                         |
| `config/viper.go`                 | 19:2      | Ineffectual assignment to `err` (ineffassign)                            | `err` is assigned but never used in `viper.Unmarshal(&config)`.       |


## References 📚

| Reference                                     | Link                                                  |
|-----------------------------------------------|-------------------------------------------------------|
| Golangci checks GitHub Repository               | [GitHub](https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/GoLang%20CI%20Checks/Static-Code-Analysis/README.md)  |
| Go Blog on Linting                           | [Go Blog](https://blog.golang.org/lint)               |
| Static Analysis Tools for Go                 | [Static Analysis](https://golang.org/doc/code.html#staticanalysis) |
| CI/CD Best Practices                          | [Atlassian](https://www.atlassian.com/continuous-delivery/ci-vs-ci) |

## 📧 Contact Information

For more information on how to implement or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |

