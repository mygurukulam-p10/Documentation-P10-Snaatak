# Ansible Role to setup Jenkins (Ubuntu)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 20-09-24    | version 1  | Amit Nagar      | 20-09-24       |


***
## Table of Contents
+ [Introduction](#Introduction)
+ [Ansible and Jenkins](#Ansible-jenkins)
+ [System Requirements](#system-requirements)
+ [Setup Ansible Role](#steps)
+ [Output Verification](#output)
+ [Jenkins Setup](#post-installation-setup)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***

# Introduction
This role is designed to automate the installation and configuration of Jenkins on target ubuntu servers. Whether you're setting up Jenkins for continuous integration, continuous delivery, or other purposes, this role aims to simplify the process.

## Ansible and Jenkins

Here, we harness the efficiency of Ansible, an open-source automation tool streamlining configuration management and application deployment. In parallel, Jenkins excels in facilitating continuous integration and delivery, ensuring a seamless and automated pipeline for software development processes.



## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 15GB                   |
| OS                       | Ubuntu(22.04)          |

***
# Steps 

**Step 1: Create a folder and initialize role inside it**
```
mkdir <dir_name>
ansible-galaxy init <RoleName>
```
 **Step 2:  AWS EC2 Inventory**
 
- Create a file called aws_ec2.yaml for the dynamic inventory inside your root folder

![Screenshot from 2024-09-22 02-18-33](https://github.com/user-attachments/assets/c3e33a95-5c40-48fe-bd01-24d4b765f998)


**Step 3: Create playbook**
* This file is defining a set of tasks to be executed on hosts belonging to the _jenkins_server group.
  ![Screenshot from 2024-09-22 02-26-48](https://github.com/user-attachments/assets/e5fd8f2b-15c0-4a42-a458-7904270ffd70)








      
