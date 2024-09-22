# Setup Version Control System - GITHUB

![image](https://github.com/user-attachments/assets/3a170719-a472-4a0c-8a38-1906e6bc461e)

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

## 1. 🎯 Purpose of the Document

The purpose of this document is to guide users in setting up and managing a version control system using GitHub. As we progress in our sprints, we will have multiple micro-repositories that will reflect team collaboration. Therefore, we are adopting GitHub, which will be more beneficial for our team and facilitate better maintenance of repositories.

## 2. 🔧 Prerequisites


| Name  | Version | Description                                 |
|-------|---------|---------------------------------------------|
| Git   | 2.34    | Distributed version control system          |
| GitHub Account | N/A     | Platform for hosting Git repositories |

## 3. ✨ Setting Up GitHub Version Control

### 1. ⚙️ Create a GitHub Account

#### 🖥️ UI Setup:
- Go to [GitHub](https://github.com).
- Click on **"Sign up"** and fill in the required details (username, email, password).
- Verify your email address.

#### 💻 CLI Setup:
- You don't need a CLI for account creation, but you can use GitHub's CLI tool later.

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

