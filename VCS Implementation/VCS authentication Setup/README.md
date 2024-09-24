# 🚀 Setup authenticaion in Version Control System - GITHUB


## Table of Contents

1. [Purpose of the Document](#1-purpose-of-the-document)
2. [Prerequisites](#2-prerequisites)
   - [GitHub Account](#github-account)
   - [Git Installation](#git-installation)
3. [Setting Up GitHub Authentication for web access](#3-Setting-up-github-authentication-for-web-access)
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



This document outlines the steps and benefits of implementing Two-Factor Authentication (2FA) for web access and Secure Shell (SSH) for command-line interface (CLI) access to enhance the security of your GitHub account.## 2. 🔧 Prerequisites


| Name  |  Description                                 |
|-------|---------------------------------------------|
| Git   |  Distributed version control system          |
| GitHub Account | Platform for hosting Git repositories |
| Mobile phone | For a TOTP app to Install |
| OpenSSH | Software Dependency for SSH Connection |

## 1. ✨ Setting Up GitHub Authentication for web access 


## 1. ✨ Setting Up GitHub Authentication for CLI

### Generating and Using SSH Keys 

Open terminal on your Machine and run below command to **generate ssh public and private key** which by default get added to **.ssh** directory of the user. Simply hit enter for the prompt or you can define your own values if needed.

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
![image](https://github.com/user-attachments/assets/5d5cf281-3998-497e-bf12-6f69f59deccd)

**Add the Public Key to GitHub/GitLab/Bitbucket**

See and copy content of your public SSH key with below command
 
``` 
cat ~/.ssh/id_rsa.pub
```
![image](https://github.com/user-attachments/assets/6a6f6659-d826-45b2-972e-8347ea6ca99a)

Paste it in your Git accounts, at SSH key section which you can find in settings of your account.

![image](https://github.com/user-attachments/assets/5dc9d303-c3fd-4d5f-946d-7290c020308e)

Choose for new SSH key and provide a title for your key and then choose for key type and paste the key in key bar and hit add SSH key button.
Enter account password when prompted.

![image](https://github.com/user-attachments/assets/fd6e4284-f83c-412e-bc28-597c8a311c5c)


**Try cloning any Repository with ssh Option**

Copy SSH URL 
![image](https://github.com/user-attachments/assets/37840952-add4-427e-bee8-d6d0a8b2b0ef)

Now when you clone the repo it won't ask for password and will provide secure login with SSH.
![image](https://github.com/user-attachments/assets/692969dc-3dd5-4ad7-9d13-26fb8c2de287)

## 6. 🏁 Conclusion

By using 2FA for web access and SSH for CLI access, we can significantly improve the security of your GitHub account. This combination provides a strong defense against unauthorized access.

## 7. 📚 Reference

| Title                                 | Link                                                                                           |
|---------------------------------------|------------------------------------------------------------------------------------------------|
| Two-Factor Authentication (2FA)      | [GitHub 2FA Documentation](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication) |
| SSH Key Generation                    | [Generating a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key) |

## 8. 📧 Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | abhinav.singh.snaatak@mygurukulam.co           |
