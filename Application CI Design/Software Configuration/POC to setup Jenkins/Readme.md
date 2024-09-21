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

**Step 1: Create a folder**
```
mkdir <dir_name>
```
 **Step 2:  AWS EC2 Inventory**
 
- Create a file called aws_ec2.yaml for the dynamic inventory inside your root folder

![Screenshot from 2024-09-22 02-18-33](https://github.com/user-attachments/assets/c3e33a95-5c40-48fe-bd01-24d4b765f998)


**Step 3: Create playbook**
* This file is defining a set of tasks to be executed on hosts belonging to the _jenkins_server group.
  ![Screenshot from 2024-09-22 02-26-48](https://github.com/user-attachments/assets/e5fd8f2b-15c0-4a42-a458-7904270ffd70)


**step 4: Create ansible role in directory we have created**
```
ansible-galaxy init <RoleName>
``
![Screenshot from 2024-09-22 02-19-09](https://github.com/user-attachments/assets/a34204b4-3b45-4ca8-9723-c3927ac47683)

**Step 5: Tasks**
1. `main.yml`: This main.yml file is acting as an orchestrator, importing tasks from the `install_jenkins.yml` file. This separation of tasks into different files is a good practice for better organization, especially when dealing with complex configurations or roles.



2. `vars` variables: 

```yaml
---
# defaults file for jenkins
jenkins_repo_url:  deb https://pkg.jenkins.io/debian-stable binary/ 
jenkins_repo_key_url:  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key 
```

> [!NOTE]
> To customize the Jenkins version based on your specific requirements, you can override these default values in your playbook. This is particularly useful when you want to install a different version of Jenkins.


3. `install_jenkins.yml`: This file is included in the jenkins/tasks/main.yml file

```yaml
---
# Update APT cache
- name: Update APT cache
  apt:
    update_cache: yes

# Installs jdk if not installed already
- name: Ensure jdk is installed
  apt:
    name: default-jre
    state: present

# Adds the Jenkins repository's GPG key to the APT keyring
- name: Add Jenkins apt key in system.
  apt_key:
    url: "{{ jenkins_repo_key_url }}"
    state: present

# Add Jenkins apt repository
- name: Add Jenkins apt repository.
  apt_repository:
    repo: "{{ jenkins_repo_url }}"
    state: present
    update_cache: yes

# Install Jenkins
- name: Install jenkins 
  apt:
    name: jenkins
    state: present 

# Start Jenkins service
- name: Start service 
  service:
    name: jenkins 
    state: started 
    enabled: yes 

# Check Jenkins service status
- name: Check Jenkins service status
  systemd:
    name: jenkins
    state: started
  ignore_errors: yes
  register: jenkins_service_status

# Display Jenkins service status
- name: Display Jenkins service status
  debug:
    var: jenkins_service_status
```

**Step 6: Playbook Execution**

* To set up Jenkins on your target servers, you will execute the Ansible playbook using the following command:

```bash
ansible-playbook -i aws_ec2.yml playbook.yml
```






      
