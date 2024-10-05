# Code Compilation- scripted Jenkins Pipeline <img width="51" alt="image" src="https://github.com/user-attachments/assets/ce666869-4766-4f9d-9bfa-3627a76843f0">


---  

| ✍Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar | 05-10-2024  | Version 1  | Amit Nagar   | 05-10-2024     |


## ⚙️ Pre-requisites

| Requirement         | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Python Version**   | Python 3.10 or later.                                                       |
| **Jenkins**          | Jenkins installed and configured.                                           |
| **Git**              | Git must be installed on the Jenkins server for repository checkout.        |
| **Python3-venv**     | Install the `python3-venv` package on the Jenkins server for virtualenv setup.|
| **pip**              | Python package installer (pip) must be available to install dependencies.   |
| **pytest**           | pytest and pytest-cov packages must be installed for testing and coverage.  |
| **Git Credentials**  | Add your GitHub credentials (e.g., `git-token`) in Jenkins for repository access.|

---

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU (4-core recommended)                           |
| **Memory (RAM)**     | Minimum 4 GB (8 GB recommended)                                   |
| **Storage**          | Minimum 20 GB of free disk space (SSD recommended for performance)|
| **Operating System** | Ubuntu 20.04 or later (or any compatible Linux distribution)      |



---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Code compilation](#-steps-to-conguration-code-compilation)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)


# Steps to Configuration Code Compilation
### 1. 🚀 Open your Jenkins Dashboard.


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Code Compilation`).



### 3. 🚀 Provide a description for the pipeline in detail what will perform.


### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for code coverage in the pipeline configuration...>Click on Save to store the configuration.



### 5. 🚀 Then Click on build to run the pipeline to perform



### 6.🚀 Now we are able to see build complete-



### 7.🚀 Click on Console Output to see the complete build.



### 8.🚀 Review the stages of the build process in the console output.

---
