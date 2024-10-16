# Go-lang - Declarative Jenkins Pipeline for Unit Testing 


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Aayush Gaur| 15-10-2024  | Version 1  | Aayush Gaur    | 15-10-2024   |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Declarative pipelines for Unit Testing](#-steps-to-configuration-declarative-pipelines-for-unit-testing)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Go-Lang Unit Testing. Jenkins, as a popular automation server, supports a variety of build configurations.


## ⚙ Pre-requisites
1. **Jenkins**: Ensure you have a Jenkins running.
2. **golang**: Ensure you have go-lang 

## 🔍 System Requirements
| Hardware Specifications | Minimum Requirement  |
|-------------------|---------------------------|
| **Processor**     | Dual-core CPU             | 
| **Memory**        | 2 GB RAM                  | 
| **Disk Space**    | 10 GB                      | 
| **OS**            |Ubuntu 22.04 LTS           |

## 💥 Steps to Configuration Declarative pipelines for Unit Testing

### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**. 
 **Enter a name for your job (e.g., `Unit Testing`)**.
![Screenshot from 2024-10-16 14-22-09](https://github.com/user-attachments/assets/31d94ee8-a5cf-4cd2-99e8-d0a994ea7264)

### 3. 🚀 Provide a description for the pipeline detailing what it will perform.
![Screenshot from 2024-10-16 14-23-26](https://github.com/user-attachments/assets/812973d8-a4e6-43b8-b3c6-9430f74c9cf5)

### 4. 🚀 Choose **Pipeline** as the job type. 
**Add your pipeline script for unit testing in the pipeline configuration.** 
**Click on **Save** to store the configuration.**
![Screenshot from 2024-10-16 14-29-40](https://github.com/user-attachments/assets/52fafceb-8cca-4c2b-91d4-eac5fc82dcbd)
![Screenshot from 2024-10-16 14-30-08](https://github.com/user-attachments/assets/478c998b-7703-4ffe-b41d-bf7ff878ef5a)

### 5. 🚀 Click on Build to run the pipeline for unit testing.

### 6. 🚀 Now, you should be able to see the build complete.
