# VCS Authentication Setup POC

![image](https://github.com/user-attachments/assets/338a5d67-4fd9-4083-a9eb-5d2d8d830785)


|  Author        | Created on |  Version  | Last updated by   |   Last edited on   |
|----------------|------------|-----------|-------------------|--------------------|
| Abhinav Singh  |  12-09-24  | version 1 |   Abhinav Singh   |      16-09-24      |

## Table of Contents
1. [Purpose](#purpose)
2. [System Prerequisites](#system-prerequisites)
3. [Step by Step Authentication Setup](#step-by-step-authentication-setup)
4. [Best Practices for Secure Authentication](#best-practices-for-secure-authentication)
5. [Conclusion](#conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)

## Purpose
VCS employs various methods to control repository access. This guide covers authentication methods used in git, their setup, and security best practices. Ensure only authorized users can interact with your repositories.

## System-Prerequisites

|        Requirements           |            Recommendation            |
|-------------------------------|--------------------------------------|
|            **OS**             |                Ubuntu                |
|        **Git Version**        |            2.28 or higher            |
|   **Git Service Account**     | GitHub, GitLab, or Bitbucket account |
|   **Software Dependencies**   |      OpenSSH      |

## Authentication Methods in Git
| **Method**                  | **Description**                    | **Security Level**           | **Use Case**            |
|-----------------------------|-----------------------------------|------------------------------|--------------------------|
| **Username and Password (Deprecated)** | Deprecated due to security risks. |   Low  |   Avoid using   |
|    **SSH Key-Based Authentication**    | Secure key-pair system. |   High  | Recommended for personal and organizational repositories  |
|   **Personal Access Tokens (PAT)**    |  Scoped tokens for HTTPS authentication. |  Medium to High  |   Required for HTTPS interactions.   |

## Best Practices for Secure Authentication

| **Practice**                          | **Description**    |
|---------------------------------------|---------------------|
| **Use SSH Keys**   | Prioritize SSH keys for secure repository access                                                                            |
| **Limit PAT Scope** | Restrict PATs to essential permissions and timeframes   |
| **Rotate Credentials**  | Regularly update SSH keys and PATs                  |

## Step by Step Authentication Setup

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

## Conclusion

SSH authentication in VCS ensures secure access to repositories by using cryptographic keys instead of passwords. It offers stronger security, reducing the risk of credential exposure. As a best practice, SSH is preferred for its robust encryption and reliability in modern development workflows. 

### Contact Information
For more information, feedback, or assistance, feel free to contact:
| Name                   | Email address          |
|------------------------|------------------------|
| Abhinav Singh          | abhinav.singh.snaatak@mygurukulam.co  |


### References
| Links                                             | Descriptions                       |
|---------------------------------------------------|------------------------------------|
| https://tinyurl.com/52k4x9f5 |VCS authentication Documentation |
