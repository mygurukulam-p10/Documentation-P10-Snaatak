#  Proof of Concept (POC) for Code Compilation
![golang](https://github.com/user-attachments/assets/e431582b-cce1-48e9-9e95-ad8a47625b4d)

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 23-09-24 | version 1 | Vinay Bansal | 25-09-24 |

## 🔍 Purpose
The purpose of this document is to provide a completed guide to step code compilation.

  
## 📑 Table of Contents
- [Introduction](#introduction)
- [⚙️ Pre-Requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🛠️ Build-Time Dependency](#-build-time-dependency)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🌐 Important Ports](#-important-ports)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📧 Contact Information ](#-contact-information )
- [📚 References](#-references )


## Introduction 
* This document will guide you through a Proof of Concept (PoC) for setting up and compiling . We will cover the necessary prerequisites, including Golang installation, as well as the basic project structure.

## ⚙ Pre-Requisites

- Go installed on your machine.
- Familiarity with Go modules.

## 🖥 System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4 GB                    |
| Disk                     |10 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠 Build-Time Dependency

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
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```

### Step 2: Change Directory
Change Directory to where your code is
```
cd salary-api
```

### Step 3: now we have to do Code Compilation
This command compiles the source code of the project according to the settings defined in the pom.xml file.
```
go build
./employee-api```
```
![ccsuccess](https://github.com/user-attachments/assets/3089ecee-144a-4fc4-a54d-fec1eff6539f)




##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## 📚 References
| Links | Descriptions|
|------|---------------------|
| Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/GoLang%20CI%20Checks/Code%20compilation%20Doc/readme.md|

