# 🚀 Setup Version Control System - GITHUB

![image](https://github.com/user-attachments/assets/3a170719-a472-4a0c-8a38-1906e6bc461e)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 26-09-24    | Version 1  | Komal Jaiswal   | 29-09-24       |

## Table of Contents

1. [Purpose of the Document](#1-purpose-of-the-document)
2. [Prerequisites](#2-prerequisites)
   - [GitHub Account](#github-account)
   - [Git Installation](#git-installation)
3. [Setting Up GitHub Version Control](#3-setting-up-github-version-control)
   1. [Create a GitHub Account](#create-a-github-account)
   2. [Install Git](#install-git)
   3. [Configure Git](#configure-git)
4. [Creating and Managing GitHub Repositories](#4-creating-and-managing-github-repositories)
   1. [Create a New Repository (UI Setup)](#create-a-new-repository-ui-setup)
   2. [Link Local Repository to GitHub (CLI Setup)](#link-local-repository-to-github-cli-setup)
5. [Security Recommendations](#5-security-recommendations)
   1. [Enable Two-Factor Authentication (2FA)](#enable-two-factor-authentication-2fa)
   2. [Use SSH for Authentication](#use-ssh-for-authentication)
   3. [Regularly Review Permissions](#regularly-review-permissions)
   4. [Keep Your Software Updated](#keep-your-software-updated)
6. [Conclusion](#6-conclusion)
7. [Reference](#7-reference)
8. [Contact](#8-contact)

## 1. 🎯 Purpose of the Document

The purpose of this document is to guide users in setting up and managing a version control system using GitHub. As we progress in our sprints, we will have multiple micro-repositories that will reflect team collaboration. Therefore, we are adopting GitHub, which will be more beneficial for our team and facilitate better maintenance of repositories.

## 2. 🔧 Prerequisites


| Name  | Version | Description                                 |
|-------|---------|---------------------------------------------|
| Git   | 2.34.1    | Distributed version control system          |
| GitHub Account | N/A     | Platform for hosting Git repositories |

## 3. ✨ Setting Up GitHub Version Control

### 1. ⚙️ Create a GitHub Account

#### 🖥️ UI Setup:
- Go to [GitHub](https://github.com).
- Click on **"Sign up"** and fill in the required details (username, email, password).
- Verify your email address.

![image](https://github.com/user-attachments/assets/7a3b793f-1f6f-43e6-8a69-be7e3f19aeb7)

---

### 2. ⚙️ Install Git

#### 🖥️ UI Setup:
- Download Git from the official [Git website](https://git-scm.com/downloads) and follow the installation instructions for your operating system.

#### 💻 CLI Setup:

**For Ubuntu:**
```
sudo apt update
sudo apt install git
```
![image](https://github.com/user-attachments/assets/5a38bf54-d5e8-4af9-bc70-e631207b6cf7)

---

### 3. ⚙️ Configure Git 

#### 🖥️ CLI Setup 

```
#### Set your Git username globally (for all repositories)
git config --global user.name "Your Name"   
##### This command sets your name for Git commits. Replace "Your Name" with your actual name.
##### Using global config means this username will apply to all repositories on your machine.
```

```
#### Set your Git email globally (for all repositories)
git config --global user.email "your_email@example.com"   
##### This command sets your email for Git commits. Replace with your actual email.
##### Using global config ensures consistency across all your projects, so you don't have to set it for each one.
```

![image](https://github.com/user-attachments/assets/4bf6af48-9fed-40e4-ac04-7ae5b0ca4751)

### Note :- We can also use Local credentials which will be applied to a specific repository. 
```
git config user.name "Work Name"
git config user.email "work_email@example.com"
```

## 4. ✨ Creating and Managing GitHub Repositories

### 1. 📁 Create a New Repository

#### 🖥️ UI Setup:
- Log in to GitHub.
- Click on the **"+"** icon in the upper right corner and select **"New repository."**
- Fill in the repository name, description, and set it as public or private.
- Initialize the repository with a README if desired.
- Click **"Create repository

![Git setup](https://github.com/user-attachments/assets/59881fc1-9b94-41a7-bd3b-74eaae016ed8)

#### 💻 CLI Setup:

```
mkdir your-repo
cd your-repo
git init
echo "# Your Repository Title" >> README.md
git add README.md
git commit -m "Initial commit"
```
![image](https://github.com/user-attachments/assets/58ece8e0-ac04-45b6-97d6-1bfcf8f26560)

---

### 2. 🔗 Link Local Repository to GitHub

#### 💻 CLI Setup:

```
git remote add origin https://github.com/username/your-repo.git
git branch -M main
```
![image](https://github.com/user-attachments/assets/6dcca27d-c81c-4ac1-bb8c-50cbaf4a9fd7)


## 5. 🔒 Security Recommendations

### 1. Enable Two-Factor Authentication (2FA):

- Go to your GitHub account settings.
- Navigate to **"Security"** and enable **"Two-factor authentication."**

![image](https://github.com/user-attachments/assets/d62a2b01-513d-42aa-b60a-9443cce5a0d5)

### 2. Use SSH for Authentication:

- **Generate an SSH key:**
```
ssh-keygen                                                                                                                  
```
![image](https://github.com/user-attachments/assets/cd6314d5-3203-4067-a04a-906cc64201a5)

- **Copy your SSH key to your clipboard:**

```
cat ~/.ssh/id_rsa.pub | clip  
```

- Click on your Github Settings , Go to SSH and GPG keys.
- Then Click on New SSH and Then paste your SSH Key.

![image](https://github.com/user-attachments/assets/2cfe7f14-32e7-400e-ba67-37ab8fa79938)


### 3. Regularly Review Permissions:

- Check and manage repository permissions and collaborators.

### 4.  Keep Your Software Up to Date:

- Regularly update Git and any development tools you use.

## 6. 🏁 Conclusion
This document provides a comprehensive guide for setting up and managing a version control system using GitHub. By following the outlined steps and implementing security recommendations, we can effectively collaborate and maintain our codes which we will be using our sprints micro repositories.

## 7. 📚 Reference

| Title                                 | Link                                                                                           |
|---------------------------------------|------------------------------------------------------------------------------------------------|
| Git Installation                      | [Git Downloads](https://git-scm.com/downloads)                                              |
| GitHub Account Creation               | [Create a GitHub Account](https://github.com/join)                                          |
| Two-Factor Authentication (2FA)      | [GitHub 2FA Documentation](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication) |
| SSH Key Generation                    | [Generating a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key) |
| Features of VCS                       | [Feature of VCS](https://github.com/mygurukulam-p10/Documention/blob/main/VCS%20Design%20%2B%20POC/Features%20of%20VCS/POC%20to%20setup%20recommeded%20VCS%20as%20per%20conclusion%20doc/README.md) |

## 8. 📧 Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |
