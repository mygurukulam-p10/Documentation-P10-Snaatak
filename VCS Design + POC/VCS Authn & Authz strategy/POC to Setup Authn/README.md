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
   * [OAuth Athentication](#oauth-authentication)
   * [GPG Signing for Commit Verification](#gpg-signing-for-commit-verification)
5. [Setting up Authentication](#setting-up-authentication)
   * [Generating and Using SSH Keys](#generating-and-using-ssh-keys)
   * [Using Personal Access Tokens (PAT)](#using-personal-access-tokens-(pat))
   * [Setting Up GPG for Signed Commits](#setting-up-gpg-for-signed-commits)
   * [Using OAuth for Application Access](#using-oauth-for-application-access)
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

**OAuth** - Secure access for third-party apps without sharing credentials.

**GPG Signing** - Verifies commit authenticity with digital signatures.

## System-Prerequisites

|        Requirements           |          Recommendation              |
|-------------------------------|--------------------------------------|
|   **OS**                      | Ubuntu, macOS, Windows               |
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

	```
	ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
	```
 
**Add the Public Key to GitHub/GitLab/Bitbucket**

See and copy content of your ssh key with below command
 
``` 
cat ~/.ssh/id_rsa.pub
```
 
Paste it in your Git service's SSH key section.
	
**Test SSH Connection**

	```
	ssh -T git@github.com
	```
### Using Personal Access Tokens (PAT)

**Generate PAT** - Go to your Git service account settings and generate a new Personal Access Token with the required permissions.

**Using PAT in Git Commands** -

For Git operations over HTTPS, use the PAT as your password -
```
git clone https://github.com/user/repo.git
```
When prompted for a password, enter the generated token.
	
### Setting Up GPG for Signed Commits

**Install GPG**

```
sudo apt install gnupg
```
 
**Generate GPG Key**

```
gpg --full-generate-key
```
 
**Configure Git to Use GPG**

```
git config --global user.signingkey <GPG_KEY_ID>
git config --global commit.gpgSign true
```
 
**Sign Commits**
```
git commit -S -m "Your signed commit message"
```
	
### Using OAuth for Application Access

**Third-Party Access** - When a third-party tool requests access to your repository, authenticate using OAuth.

**Grant Permissions** - Review and grant the appropriate permissions to the tool to access your repositories.
	
## Common Authentication Errors and Solutions

|             **Error Message**           |           **Cause**                     |                 **Solution**                  |
|-----------------------------------------|--------------------------------------|---------------------------------------------------|
|   **Permission denied (publickey)**     |  SSH keys not correctly configured       |Ensure your public key is added to Git service.  |
|**fatal: Authentication failed for...**  |Incorrect credentials or token expired    |         Update credentials or regenerate PAT.   |
|   **gpg: no valid OpenPGP data found**  |  GPG key not properly configured        |Check the GPG key setup and configure correctly.  |
|   **OAuth access error**                | Third-party tool access token invalid     | Re-authenticate using OAuth or renew token.    |

## Best Practices for Secure Authentication

**Use SSH Keys for Git Operations** - SSH keys are highly secure and recommended for accessing repositories.

**Enable Two-Factor Authentication (2FA)** - On your Git service account, enable 2FA for additional security.

**Limit the Scope of Personal Access Tokens** - Always restrict the scope and duration of PATs to minimize the risk if a token is compromised.

**Regularly Rotate Tokens and Keys** - Periodically regenerate your SSH keys and PATs to ensure security.

**Sign Commits with GPG** - Especially in larger projects, ensure commits are signed and verified to prevent unauthorized changes.

**Use OAuth for Third-Party Applications** - Instead of sharing your credentials, use OAuth to grant limited access to third-party tools.

## Conclusion

Authentication in VCS ensures secure access to repositories using various methods like SSH keys, Personal Access Tokens (PAT), OAuth, and GPG commit signing. While traditional username/password authentication is deprecated, modern methods such as SSH and PATs provide enhanced security. This document details the setup process for each method, troubleshooting common issues, and best practices such as enabling two-factor authentication (2FA) and signing commits with GPG. By following these guidelines, you can effectively secure your Git interactions and safeguard your repositories.

