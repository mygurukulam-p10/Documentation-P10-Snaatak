# VCS Authentication Setup POC


|  Author        | Created on |  Version  | Last updated by  | Last edited on |
|----------------|------------|-----------|------------------|----------------|
| Abhinav Singh  |   12-09-24 | version 1 |   Abhinav Singh  |     13-09-24   |

## Table of Contents
1. [Purpose](#purpose)
2. [Authentication Overview](#authentication-overview)
3. [System Prerequisites](#system-prerequisites)
4. [Authentication Methods in Git](#authentication-methods-in-git)
   * [Username and Password (Deprecated)](#username-and-password-(deprecated))
   * [SSH Key-Based Authentication](#ssh-key-based-authentication)
   * [Personal Access Tokens (PAT)](#personal-access-tokens-(pat))
   * [GPG Signing for Commit Verification](#gpg-signing-for-commit-verification)
5. [Setting up Authentication](#setting-up-authentication)
   * [Generating and Using SSH Keys](#generating-and-using-ssh-keys)
   * [Using Personal Access Tokens (PAT)](#using-personal-access-tokens-(pat))
   * [Setting Up GPG for Signed Commits](#setting-up-gpg-for-signed-commits)
6. [Common Authentication Errors and Solutions](#common-authentication-errors-and-solutions)
7. [Best Practices for Secure Authentication](#best-practices-for-secure-authentication)
8. [Conclusion](#conclusion)
## Purpose
Git is a distributed version control system that uses various authentication methods to manage access to repositories hosted on remote services like GitHub, GitLab, Bitbucket, and others.

These authentication methods ensure that only authorized users can interact with repositories, securing actions such as cloning, pushing, pulling, and managing code.

This document outlines all the authentication methods in Git, their setup, and best practices to maintain security.

## Authentication Overview

Git authentication has evolved from older methods like username/password (now deprecated) to more secure, modern options, including:-

**SSH Keys** - Secure key-based access.

**Personal Access Tokens (PAT)** - Token-based login for HTTPS with customizable permissions.

**GPG Signing** - Verifies commit authenticity with digital signatures.

## System-Prerequisites

|        Requirements           |          Recommendation              |
|-------------------------------|--------------------------------------|
|   **OS**                      | Ubuntu           |
|   **Git Version**             | 2.28 or higher                       |
|   **GPG**                     | Installed for commit signing         |
|   **Git Service Account**     | GitHub, GitLab, or Bitbucket account |
|   **Software Dependencies**   | OpenSSH, GPG (for signing)           |

## Authentication Methods in Git

### Username and Password (Deprecated)

This method involves using Git service username and password for HTTPS authentication. 
It has been deprecated by most Git services due to security concerns, as passwords can easily be compromised.

### SSH Key-Based Authentication -

**Description** - SSH authentication uses a key-pair system where the private key remains on your machine, and the public key is added to your Git service account. It is one of the most secure methods of authentication.

**Security Level** - High

**Use Case** - Recommended for both personal and organizational repositories, especially for secure communications over networks.

### Personal Access Tokens (PAT)

**Description** - A PAT is a token that serves as a password alternative when using HTTPS to interact with Git repositories. Tokens are scoped, meaning you can control what permissions a token has (read, write, etc.).

**Security Level** - Medium to High

**Use Case** - Required when using Git services over HTTPS instead of SSH.

### OAuth Authentication

**Description** - OAuth allows third-party applications to request limited access to your Git repositories without requiring you to share your password or tokens directly.

**Security Level** - High

**Use Case** - Used for integrating third-party applications, CI/CD pipelines, or developer tools.

### GPG Signing for Commit Verification

**Description** - GPG (GNU Privacy Guard) allows developers to sign their commits, verifying their authenticity. This is especially useful in large projects where it's crucial to ensure that commits come from trusted sources.

**Security Level** - High for Commit Integrity

**Use Case** - Recommended for teams or projects where commit authenticity and integrity are paramount.

## Setting up Authentication

### Generating and Using SSH Keys

**Generate SSH Key** 

Open terminal on your Machine and run below command to generate ssh public and private key which by default get added to **.ssh** directory of the user. Simply hit enter for the prompt or you can define your own values if needed.

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

Paste it in your Git accounts, SSH key section which you can find in settings of your account.

![image](https://github.com/user-attachments/assets/5dc9d303-c3fd-4d5f-946d-7290c020308e)

Choose for new SSH key and provide a title for your key and then choose for key type and paste the key in key bar and hit add SSH key button.
Enter account password when prompted.

![image](https://github.com/user-attachments/assets/fd6e4284-f83c-412e-bc28-597c8a311c5c)


**Try cloning any Repository with ssh Option**

Copy SSH URL 
![image](https://github.com/user-attachments/assets/37840952-add4-427e-bee8-d6d0a8b2b0ef)

Now when you clone the repo it won't ask for password and will provide secure login with SSH.
![image](https://github.com/user-attachments/assets/692969dc-3dd5-4ad7-9d13-26fb8c2de287)


### Using Personal Access Tokens (PAT)

**Generate PAT** - Go to your Git service account settings and generate a new Personal Access Token with the required permissions.
![image](https://github.com/user-attachments/assets/b591d8cf-78e8-4a46-96b1-2ee1f67f27e2)

Choose Generate new token (Classic) and enter password when prompted.

Then add a description for your token, define expiration time and select appropriate permissions in **select scopes** section and hit generate token.
![image](https://github.com/user-attachments/assets/ae58e648-55d4-4165-af41-b835448c6dde)

Copy and save newly generated token.
![image](https://github.com/user-attachments/assets/e0d37cba-fbb4-43a7-8dad-c05041df7440)

**Using PAT in Git Commands** -

For Git operations over HTTPS, use the PAT as your password -
```
git clone https://github.com/user/repo.git
```
When prompted for a password, enter the generated token.
![image](https://github.com/user-attachments/assets/66fa2ac4-526c-4c7f-9730-089a3df9c570)
	
### Setting Up GPG for Signed Commits

**Install GPG**

```
sudo apt install gnupg
```
![image](https://github.com/user-attachments/assets/090718b9-770a-4fa5-810e-66bf7840aff9)

 
**Generate GPG Key**

```
gpg --full-generate-key
```

Choose appropriate options of your choice

![image](https://github.com/user-attachments/assets/65051500-f613-477b-b6b4-278501c63790)

**List your GPG keys**

```
gpg --list-secret-keys --keyid-format LONG
```
![image](https://github.com/user-attachments/assets/04053cdc-cb31-4a51-9ec0-a1cf09064c38)

**Configure Git to Use GPG and enable automatic signing of all commits**

```
git config --global user.signingkey <GPG_KEY_ID>
git config --global commit.gpgSign true
```
![image](https://github.com/user-attachments/assets/1e4f2655-d925-4956-a383-9a523d4df0a4)

**Export your public GPG key  and Add Your GPG Key to GitHub**

```
gpg --armor --export <GPG_KEY_ID>
```
![image](https://github.com/user-attachments/assets/6b4edda5-4268-48c4-9703-481faf52affd)

Copy the key and paste it in GPG key section in your Github account settings

![image](https://github.com/user-attachments/assets/30a6a1f9-77e7-40c5-85d8-41e388d39b16)

When you make a commit, Git will now automatically sign it with your GPG key. 
You can verify that a commit is signed with below command

```
git log --show-signature
```
![image](https://github.com/user-attachments/assets/decaf2a1-53e7-44a4-bf14-750ab8a52629)
	
## Common Authentication Errors and Solutions

|             **Error Message**           |           **Cause**                     |                 **Solution**                  |
|-----------------------------------------|--------------------------------------|---------------------------------------------------|
|   **Permission denied (publickey)**     |  SSH keys not correctly configured       |Ensure your public key is added to Git service.  |
|**fatal: Authentication failed for...**  |Incorrect credentials or token expired    |         Update credentials or regenerate PAT.   |
|   **gpg: no valid OpenPGP data found**  |  GPG key not properly configured        |Check the GPG key setup and configure correctly.  |

## Best Practices for Secure Authentication

**Use SSH Keys for Git Operations** - SSH keys are highly secure and recommended for accessing repositories.

**Enable Two-Factor Authentication (2FA)** - On your Git service account, enable 2FA for additional security.

**Limit the Scope of Personal Access Tokens** - Always restrict the scope and duration of PATs to minimize the risk if a token is compromised.

**Regularly Rotate Tokens and Keys** - Periodically regenerate your SSH keys and PATs to ensure security.

**Sign Commits with GPG** - Especially in larger projects, ensure commits are signed and verified to prevent unauthorized changes.

## Conclusion

Authentication in VCS ensures secure access to repositories using various methods like SSH keys, Personal Access Tokens (PAT),  and GPG commit signing. While traditional username/password authentication is deprecated, modern methods such as SSH and PATs provide enhanced security. This document details the setup process for each method, troubleshooting common issues, and best practices such as enabling two-factor authentication (2FA) and signing commits with GPG. By following these guidelines, you can effectively secure your Git interactions and safeguard your repositories.

