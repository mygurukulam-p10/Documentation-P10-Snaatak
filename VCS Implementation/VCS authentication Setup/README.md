# 🚀 Setup authenticaion in Version Control System - GITHUB


## Table of Contents

1. [Purpose of the Document](#purpose-of-the-document)
2. [Prerequisites](#prerequisites)
3. [Setting Up GitHub Authentication for web access](#Setting-up-github-authentication-for-web-access)
4. [Setting Up GitHub Authentication for CLI access](#Setting-up-github-authentication-for-cli-access)
5. [Conclusion](#6-conclusion)
6. [Reference](#7-reference)
7. [Contact](#8-contact)

## Purpose of the Document


This document outlines the steps and benefits of implementing Two-Factor Authentication (2FA) for web access and Secure Shell (SSH) for command-line interface (CLI) access to enhance the security of your GitHub account.

## Prerequisites


| Name  |  Description                                 |
|-------|---------------------------------------------|
| Git   |  Distributed version control system          |
| GitHub Account | Platform for hosting Git repositories |
| Mobile phone | For a TOTP app to Install |
| OpenSSH | Software Dependency for SSH Connection |

##  Setting Up GitHub Authentication for web access 

### Enabling Two-factor authentication

Go to github sign in page and,

Signin into your Github account with username/email and Password.
![image](https://github.com/user-attachments/assets/d227944b-4185-40be-98a5-ee89eb16c0db)

Navigate to settings page and choose Password and Authentication
![image](https://github.com/user-attachments/assets/ff41b1a6-bd62-46af-ba7d-d2a43f32ec11)

Under Two-factor Authentication Section You will see different options to choose -

You need to Install any Authenticator app on your mobile phone in my case **Authy,**

![image](https://github.com/user-attachments/assets/ed3df626-6528-4f77-a2c9-5950fcd5dbc8)


Now open the authenticator app select add account and Capture the QR Code present under Two-factor authentication section
![image](https://github.com/user-attachments/assets/3c4c7811-2bc3-4f9b-baa2-0805e832c3ac)

Complete Enablement.


##  Setting Up GitHub Authentication for CLI Access

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

##  Conclusion

By using 2FA for web access and SSH for CLI access, we can significantly improve the security of your GitHub account. This combination provides a strong defense against unauthorized access.

##  Reference

| Title                                 | Link                                                                                           |
|---------------------------------------|------------------------------------------------------------------------------------------------|
| Two-Factor Authentication (2FA)      | [GitHub 2FA Documentation](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication) |
| SSH Key Generation                    | [Generating a new SSH key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key) |

## Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

|  Name   | Email Address                                  |
|---------|------------------------------------------------|
| Abhinav | abhinav.singh.snaatak@mygurukulam.co           |
