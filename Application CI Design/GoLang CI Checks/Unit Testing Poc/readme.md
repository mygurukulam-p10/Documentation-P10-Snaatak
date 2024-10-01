#  Proof of Concept (POC) for Unit Testing for Golang
![image](https://github.com/user-attachments/assets/2cc227ca-7629-47af-811b-624b25ba6e9c)

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 01-10-24 | version 1 | Vinay Bansal | 02-10-24 |

## 🔍 Purpose
We are preparing this document so that we can easily provide a completed guide to step Unit Testing which is designed in GoLang to manage employee-api information.

  
## 📑 Table of Contents
- [Introduction](#introduction)
- [⚙️ Pre-Requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🛠️ Dependencies](#-dependencies)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📝Conclusion](#conclusion)
- [📧 Contact Information ](#-contact-information )
- [📚 References](#-references )


## Introduction 
* This document will guide you through a Proof of Concept (PoC) for setting up and compiling . We will cover the necessary prerequisites, dependency, Architecture as well as the basic project structure.

## ⚙ Pre-Requisites

- Go installed on your machine.
- Familiarity with Go modules.

## 🖥 System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 2 GB                    |
| Disk                     |5 GB free disk space                  |
| OS                       | Ubuntu 22.04 LTS         |


## 🛠 Dependencies

| Name     | Version | Description                              |
|----------|---------|------------------------------------------|
| Golang   | 1.18.1  | Programming language for the application |


## 🏗 Architecture


## 📥 Step-by-step Installation

## Install git
```
sudo apt install git
```
### 📂 Step 1: Clone the Git Repository
```
https://github.com/OT-MICROSERVICES/employee-api.git
```

### Step 2: Change Directory
Change Directory to where your code is
```
cd employee-api
```
### Step 3: Install Golang

- Update your system
```
sudo apt update
sudo apt upgrade -y
```

- Download the Go 1.20 tarball
```
wget https://go.dev/dl/go1.20.linux-amd64.tar.gz
```

- Extract the tarball to /usr/local
```
sudo tar -C /usr/local -xzf go1.20.linux-amd64.tar.gz
```

- Add Go to your PATH
```
echo "export PATH=\$PATH:/usr/local/go/bin" >> ~/.profile
source ~/.profile
```

- Verify the installation
```
go version
```


### Step 4: Unit Testing


##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

## 📚 References
| Links | Descriptions|
|------|---------------------|
| Document|https://github.com/mygurukulam-p10/Documention/blob/main/Application%20CI%20Design/GoLang%20CI%20Checks/Unit%20Testing%20Doc/readme.md|

