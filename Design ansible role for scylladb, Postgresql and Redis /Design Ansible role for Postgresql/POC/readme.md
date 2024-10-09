
# Ansible Role for Postgresql

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 09-10-2024  | Version 1  | Vinay Bansal    | 09-10-2024     |


***
## Table of Contents
+ [Introduction](#introduction)
+ [System Requirements](#system-requirements)
+ [Runtime Dependency](#runtime-dependency)
+ [Flow_Diagram](#flow-diagram)
+ [Setup Ansible Role](#steps)
+ [Output Verification](#output)
+ [Jenkins Setup](#post-installation-setup)
+ [Conclusion](#conclusion)
+ [Contact Information](#contact-information)
+ [References](#references)

***

# Introduction
This role is designed to automate the installation and configuration of Jenkins on target ubuntu servers. Whether you're setting up Jenkins for continuous integration, continuous delivery, or other purposes, this role aims to simplify the process.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 1GB                    |
| Disk                     | 10GB                   |
| OS                       | Ubuntu(22.04)          |

Before creating the Jenkins Ansible role, [click here](https://github.com/mygurukulam-p10/Documention/tree/main/Application%20CI%20Design/Software%20Configuration/Ansible%20role%20documentation) to read about Ansible roles.


## Runtime Dependency

| Name           | Version      | Description                                                      |
|----------------|--------------|------------------------------------------------------------------|
| Ansible        | 2.9 or higher     | Automation tool for configuration management and deployment.     |
| Python         | 3.10.12     | Required for running Ansible and executing modules.              |
| Jinja          | 3.1.4       | Templating engine used by Ansible for dynamic content generation. |
| boto3          | 1.34.98     | AWS SDK for Python, used for interacting with AWS services.      |
| pip3           | 22.0.2      |             To use pip in Ansible for installing Python packages | 


## Flow Diagram
![image](https://github.com/user-attachments/assets/d1b78e77-74c2-4b09-a4ee-eec9cc36a35a)



***
# Steps 

## Step 1: Install runtime dependencies

### Create a script to install the required dependencies
Save the following script as `dependencies.sh`:

```bash
#!/bin/bash

# Install pip
sudo apt update
sudo apt install python3-pip -y

# Install Ansible
python3 -m pip install ansible-core==2.16.7

# Install boto3 library
pip install boto3==1.34.98

# Check installed version of boto3
pip show boto3
```
- Run the above script and install the dependencies
  
![Screenshot from 2024-09-23 14-38-00](https://github.com/user-attachments/assets/283ca239-9019-4177-ae43-af9fc8fa8c44)



**Step 2: Create a folder**
```
mkdir <dir_name>
```
 **Step 3:  AWS EC2 Inventory**
 
- Create a file called aws_ec2.yaml for the dynamic inventory inside your created folder



 **Step 4: Create ansible.cfg**
- The ansible.cfg file configures Ansible settings such as inventory paths, default users, and privilege escalation options.
![Screenshot from 2024-09-23 14-43-19](https://github.com/user-attachments/assets/48ef1144-2093-4fe2-b505-57be5a9c8c4b)


**Step 5: Create playbook**
* This file is defining a set of tasks to be executed on hosts belonging to the _jenkins_server group.
  
![image](https://github.com/user-attachments/assets/76ecfb62-10be-4ded-a58c-a0294d6d0ace)


**step 6: Create ansible role in a directory we have created**
```
ansible-galaxy init <RoleName>
```
![image](https://github.com/user-attachments/assets/7cdd0703-3422-4d7e-bbf4-24b1b3706067)


![image](https://github.com/user-attachments/assets/bf47c565-16b8-41f9-863a-f4e3e25ce2f6)

**Step 7: Defaults**
**Step 8: files**
**Step 9: handlers**
- handlers/main.yaml: In this file we define our handlers.
**Step 10: meta**

**Step 11: Tasks**
1. `main.yml`: This main.yml file is acting as an orchestrator, importing tasks from the file. This separation of tasks into different files is a good practice for better organization, especially when dealing with complex configurations or roles.

```
---
# tasks file for postgresql_role
- include_tasks: install.yml
- include_tasks: configure.yml
- include_tasks: start.yml
```
2. `vars.yaml`:  The vars/main.yml file in an Ansible role is where variables specific to the role are defined.

```
# vars/main.yml
postgresql_packages:
  Debian: 
    - postgresql
    - postgresql-contrib
  RedHat: 
    - postgresql{{ postgresql_version }}
    - postgresql-contrib

postgresql_service_name:
  Debian: "postgresql"
  RedHat: "postgresql-{{ postgresql_version }}"
```




3. `install.yml`: This file is included in the jenkins/tasks/install.yml file
```
# tasks/install.yml
- name: Install PostgreSQL
  package:
    name: "{{ postgresql_packages[ansible_os_family] }}"
    state: present
  when: ansible_os_family in ['Debian', 'RedHat']
---

- `configure.yml`: This file is included in the postgresql_role/tasks/configure.yml file
```
#tasks/configure.yml
- name: Ensure PostgreSQL configuration directory exists
  file:
    path: "{{ postgresql_data_dir }}"
    state: directory
    owner: "{{ postgresql_user }}"
    group: "{{ postgresql_user }}"
    mode: '0700'

- name: Generate postgresql.conf
  template:
    src: postgresql.conf.j2
    dest: "{{ postgresql_config_file }}"
    owner: "{{ postgresql_user }}"
    group: "{{ postgresql_user }}"
    mode: '0600'
```

- `start.yml`: This file is included in the postgresql_role/tasks/start.yml file
```
#tasks/start.yml
- name: Ensure PostgreSQL is started and enabled
  service:
    name: "{{ postgresql_service_name[ansible_os_family | lower] }}"
    state: started
    enabled: true
```
**Step 11: templates**
**Step 12: tests**
**Step 13: vars**

4.handlers/main.yaml: In this file we define our handlers.

```
# handlers file for postgresql_role
- name: Restart PostgreSQL
  service:
    name: "{{ postgresql_service_name[ansible_os_family | lower] }}"
    state: restarted
```

**Step 8: Playbook Execution**


```bash
ansible-playbook -i aws_ec2.yml playbook.yml
```


## Output


## Conclusion 




## Contact Information

| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |


## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| Ansible documentation           | https://docs.ansible.com/ansible/latest/index.html    |
| Dyanmic Inventory               | https://www.youtube.com/watch?v=junPdh2yvbU&t=454s | 



      

