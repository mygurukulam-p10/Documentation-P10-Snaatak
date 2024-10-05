# Code Compilation- scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">


---  

| ✍Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar | 05-10-2024  | Version 1  | Amit Nagar   | 05-10-2024     |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Code compilation](#-steps-to-conguration-code-compilation)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)


## Introduction 
This document provides an overview of implementing code compilation in a Go project using a Jenkins declarative pipeline.
## ⚙️ Pre-requisites

| Requirement         | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Jenkins**          | Jenkins installed and configured.                                           |
| **Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access.|

---

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |


# Steps to Configuration Code Compilation
### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Code Compilation`).
![Screenshot from 2024-10-05 11-42-53](https://github.com/user-attachments/assets/85f6e0ef-e8c7-48d4-a254-a4ee7e806e3d)



### 3. 🚀 Provide a description for the pipeline in detail what will perform.
![Screenshot from 2024-10-05 11-43-43](https://github.com/user-attachments/assets/70b71bf9-2333-46f5-ab21-6ce59dd430d8)


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for code compilation in the pipeline configuration...>Click on Save to store the configuration.

![Screenshot from 2024-10-05 12-05-35](https://github.com/user-attachments/assets/57cbffb8-526d-41f1-91c4-920cf2b0b84d)



### 5. 🚀 Then Click on build to run the pipeline to perform
![Screenshot from 2024-10-05 12-11-28](https://github.com/user-attachments/assets/7548fea1-4c3e-4c87-87af-a10ce3241090)


### 6.🚀 Now we are able to see build complete-

![Screenshot from 2024-10-05 12-13-09](https://github.com/user-attachments/assets/62f3a6fa-7a94-4aa7-8b88-9dbaaaf1ebd6)


### 7.🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-05 12-07-04](https://github.com/user-attachments/assets/6bdf0edc-e00e-4cb3-8d51-f015f089da8e)

![Screenshot from 2024-10-05 12-10-02](https://github.com/user-attachments/assets/f7c9c60a-02ca-4386-94f1-9b18a85ca978)

![Screenshot from 2024-10-05 12-10-08](https://github.com/user-attachments/assets/b615a9ee-0b4b-4917-90ad-64f7fc425bb9)

### 8.🚀 Review the stages of the build process in the console output.
![Screenshot from 2024-10-05 12-10-42](https://github.com/user-attachments/assets/a4c8fb82-151a-4de0-87f7-93f29c02e03b)

---

## Conclusion
The code compilation stage successfully transforms the Go source code into an executable binary, ensuring that the application is free from syntax errors and meets the necessary requirements.

## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Go Build and Test       | [Go Build and Test Documentation](https://golang.org/doc/code.html)  |
| Go Command              | [Go Command](https://golang.org/ref/go)                |
| Jenkins Pipeline        | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
| Go Testing              | [Go Testing](https://golang.org/pkg/testing/)          |
