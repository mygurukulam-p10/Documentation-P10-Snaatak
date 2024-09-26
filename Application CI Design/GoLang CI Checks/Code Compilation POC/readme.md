#  Proof of Concept (POC) for Code Compilation

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 23-09-24 | version 1 | Vinay Bansal | 25-09-24 |
## 📑 Table of Contents

- [🔍 Purpose](#-purpose)
- [⚙️ Pre-requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🛠️ Build-Time Dependency](#-build-time-dependency)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🌐 Important Ports](#-important-ports)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📧 Contact Information](#-contact-information)

#🔍 Purpose
The Employee REST API is a Golang-based microservice that handles all employee-related transactions within the OT-Microservices. It is fully platform-independent and can be run on any platform.

## ⚙️Prerequisites

- Go installed on your machine.
- Familiarity with Go modules.

##  🖥️System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                    |
| Disk                     |10 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠️ Build-Time Dependency

| 🛠️ Name | 📦 Version | 📄 Description |
|---------|------------|----------------|
| **Go modules** | 1.20      | Make sure your Go project uses Go modules (go.mod and go.sum) for dependency management. |


## 🚀 Run-Time Dependency

| 🚀 Name | 📦 Version | 📄 Description          |
|---------|------------|--------------------------|
| **ScyllaDB** |  6.1.1  | ScyllaDB is a NoSQL database being utilized as the primary database in the employee application |

## 🌐 Important Ports

| 🔌 Inbound Traffic | 📄 Description           |
|--------------------|--------------------------|
| **9042**           | Used by ScyllaDB |

## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
https://github.com/OT-MICROSERVICES/employee-api.git
```

### Step 2: For Code Compilation
```
go build
./employee-api
```
![ccsuccess](https://github.com/user-attachments/assets/3089ecee-144a-4fc4-a54d-fec1eff6539f)




# Conclusion
The go build command is a fundamental tool in the Go development workflow, enabling developers to compile their applications efficiently. By following best practices and recommendations, such as using Go modules, optimizing build flags, and leveraging cross-compilation, developers can enhance their build processes and ensure consistent, high-quality application performance across various platforms.

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## 📚References
| Links | Descriptions|
|------|---------------------|


