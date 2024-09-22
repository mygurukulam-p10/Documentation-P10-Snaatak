# Ansible Role to setup Jenkins (Ubuntu)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 20-09-24    | version 1  | Amit Nagar      | 22-09-24       |


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

Before creating the Jenkins Ansible role, [click here](https://github.com/mygurukulam-p10/Documention/tree/main/Application%20CI%20Design/Software%20Configuration/Ansible%20role%20documentation) to read about Ansible roles.


***
# Steps 

**Step 1: Create a folder**
```
mkdir <dir_name>
```
 **Step 2:  AWS EC2 Inventory**
 
- Create a file called aws_ec2.yaml for the dynamic inventory inside your created folder

![Screenshot from 2024-09-22 02-18-33](https://github.com/user-attachments/assets/c3e33a95-5c40-48fe-bd01-24d4b765f998)


**Step 3: Create playbook**
* This file is defining a set of tasks to be executed on hosts belonging to the _jenkins_server group.
* 
  ![Screenshot from 2024-09-22 02-26-48](https://github.com/user-attachments/assets/e5fd8f2b-15c0-4a42-a458-7904270ffd70)


**step 4: Create ansible role in directory we have created**
```
ansible-galaxy init <RoleName>
```
![Screenshot from 2024-09-22 02-19-09](https://github.com/user-attachments/assets/a34204b4-3b45-4ca8-9723-c3927ac47683)

**Step 5: Tasks**
1. `main.yml`: This main.yml file is acting as an orchestrator, importing tasks from the `install_jenkins.yml` file. This separation of tasks into different files is a good practice for better organization, especially when dealing with complex configurations or roles.

![Screenshot from 2024-09-22 02-38-38](https://github.com/user-attachments/assets/8567b099-75e9-40a8-b644-4e76c2f3a288)

2. `vars.yaml`:  The vars/main.yml file in an Ansible role is where variables specific to the role are defined.

```yaml
---
# vars file for jenkins-role

dependencies:
  - curl
  - apt-transport-https
  - gnupg

jenkins_repo_key_url: "https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key"

jenkins_repo_url: "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable/ binary/"


```

> [!NOTE]
> To customize the Jenkins version based on your specific requirements, you can override these default values in your playbook. This is particularly useful when you want to install a different version of Jenkins.


3. `install_jenkins.yml`: This file is included in the jenkins/tasks/main.yml file

```yaml
---


#Installing required dependancy 

- name: Check if the all dependancy  are installed
  apt:
    name: "{{ item }}"
    state: present
  loop: "{{ dependencies}}"

- name: Add Jenkins apt repository key
  get_url:
    url: "{{ jenkins_repo_key_url }}"
    dest: /usr/share/keyrings/jenkins-keyring.asc
    mode: "0644"


- name: Add jenkins repository
  apt_repository:
    repo: "{{ jenkins_repo_url }}"
    state: present
    update_cache: yes


- name: Install JDK 17
  apt:
    name: openjdk-17-jdk
    state: present

- name: Install Jenkins
  apt:
    name: jenkins
    state: present

- name: Ensure Jenkins is started and enabled
  service:
    name: jenkins
    state: started
    enabled: true


- name: Check jenkins service status
  systemd:
    name: jenkins
    state: started
  register: jenkins_service_status



- name: Display jenkins service status
  debug:
    var: jenkins_service_status
   

- name: Get admin password
  slurp:
    src: /var/lib/jenkins/secrets/initialAdminPassword 
  register: admin_password

- name: debugging admin password
  debug:
    var: admin_password['content']


- name: setfact admin_password
  set_fact:
    jenkins_admin_password: "{{ admin_password['content'] | b64decode | trim }}"


- name: check value
  debug:
    var: jenkins_admin_password

- name: Install Jenkins plugins
  jenkins_plugin:
    name: "{{ item.key }}"
    # version: "{{ item.version }}"
    url_username: admin
    url_password: "{{ jenkins_admin_password }}"
    url: "http://localhost:8080"
    state: present
  loop:
    - { key: "gitlab-plugin" }
  register: install_result

- name: Show installation status
  debug:
    var: install_result

- name: Restart Jenkins
  systemd:
    name: jenkins 
    state: restarted

```

**Step 6: Playbook Execution**

* To set up Jenkins on your target servers, you will execute the Ansible playbook using the following command:

```bash
ansible-playbook -i aws_ec2.yml playbook.yml
```
![Screenshot from 2024-09-22 03-01-44](https://github.com/user-attachments/assets/2701f21a-89ed-4e53-9502-7a099aa34eed)


## Output
1.  **Host-level output**: Output for host would indicate whether the playbook execution was successful or not.


![Screenshot from 2024-09-22 03-05-34](https://github.com/user-attachments/assets/d9f19482-95ec-4cf9-8d38-6f6aa2d27cb8)

***
## Post-Installation Setup
* Open your web browser and navigate to `http://your-jenkins-server:8080`.

![Screenshot from 2024-09-22 03-07-15](https://github.com/user-attachments/assets/bfde866f-51f1-43a4-bdda-8bc8f093e803)

>[!IMPORTANT]
>
>Ensure that port `8080` is open on your Jenkins server.

* Retrieve the initial administrator password from the Jenkins server.
![Screenshot from 2024-09-22 03-13-39](https://github.com/user-attachments/assets/e230a9d5-33c8-4086-a6ce-c603999aa48e)

* Install required plugins and you are set
![Screenshot from 2024-09-22 03-14-53](https://github.com/user-attachments/assets/2b66ff36-efb9-40fd-acd6-b071fb746e2f)

* Login to jenkins Dashboard
![Screenshot from 2024-09-22 03-17-30](https://github.com/user-attachments/assets/0bb30c96-2e7c-48f2-9b6c-ace9149ca5c0)


***
## Conclusion 

* This guide illustrates the process of deploying Jenkins in a development environment through Ansible. By adhering to these instructions, you can effectively provision and set up Jenkins within your AWS infrastructure.


## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


## References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
| Ansible documentation           | https://docs.ansible.com/ansible/latest/index.html    |
| Jenkins Installation    | https://www.jenkins.io/doc/book/installing/linux/  |
| Dyanmic Inventory               | https://www.youtube.com/watch?v=junPdh2yvbU&t=454s | 



      
