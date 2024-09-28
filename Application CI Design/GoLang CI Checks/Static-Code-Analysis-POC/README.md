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

```
golangci-lint run 

```

![image](https://github.com/user-attachments/assets/8ba89f07-6075-43f2-bff6-df06e626d2d9)

## References 📚

| Reference                                     | Link                                                  |
|-----------------------------------------------|-------------------------------------------------------|
| Golangci checks GitHub Repository               | [GitHub](https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/GoLang%20CI%20Checks/Static-Code-Analysis/README.md)  |
| Go Blog on Linting                           | [Go Blog](https://blog.golang.org/lint)               |
| Static Analysis Tools for Go                 | [Static Analysis](https://golang.org/doc/code.html#staticanalysis) |
| CI/CD Best Practices                          | [Atlassian](https://www.atlassian.com/continuous-delivery/ci-vs-ci) |

## 📧 Contact Information

For more information on how to implement CI or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |

