# SonarQube Authentication

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 25-09-2024         | 1.0       | Aayush Gaur  |  SonarQube Authentication         |


![Screenshot from 2024-09-26 12-19-20](https://github.com/user-attachments/assets/78ffa655-6866-43c8-a443-870e3ed92f63)

## Table of Contents

1. [Introduction](#introduction)
2. [SonarQube Built-in Authentication](#sonarqube-built-in-authentication)
3. [External Authentication Methods](#external-authentication-methods)
4. [Token-Based Authentication](#token-based-authentication)
5. [SAML Authentication](#saml-authentication)
6. [Security Best Practices](#security-best-practices)
7. [Conclusion](#conclusion)
8. [Contact Information](#contact-information)
9. [References](#references)

## Introduction
**SonarQube** is a popular tool for continuous code quality inspection. It helps developers to detect bugs, code smells, and security vulnerabilities in their codebases. Ensuring secure access to SonarQube is essential for protecting the project codebase and the analysis data. This is where **authentication** comes into play.

SonarQube supports different authentication mechanisms, allowing administrators to control who has access to the platform. This document outlines various authentication methods and explains how to configure them for a secure and efficient user management system.

## SonarQube Built-in Authentication

### 1 Default Administrator Credentials
After installing SonarQube, the platform comes with a default built-in admin account with the following credentials:
- **Username**: `admin`
- **Password**: `admin`

It is crucial to change this default password to avoid unauthorized access. The administrator can change the password in the user settings after the first login.

### 2 Managing Users and Groups
SonarQube’s built-in user management allows administrators to create users and groups directly within the platform.

- **User Management**: Administrators can create, update, and delete user accounts. These users are authenticated locally by SonarQube.
- **Group Management**: Users can be assigned to groups, and administrators can control permissions at a group level, such as access to projects, administration rights, and analysis execution.

**Steps to manage users:**
1. Go to **Administration** -> **Security** -> **Users**.
2. Use the "Create" button to add new users.
3. Modify user details such as passwords, email, and group memberships.

---

## External Authentication Methods

SonarQube integrates with various external authentication providers to centralize user management and enforce corporate security policies.

### 1 LDAP/Active Directory Authentication
SonarQube can authenticate users against **LDAP** (Lightweight Directory Access Protocol) or **Active Directory (AD)**, making it easier for organizations to manage user access through a centralized directory.

**Benefits:**
- Centralized user management.
- Single sign-on experience for users.
- Synchronization of user details (groups, roles, etc.) with the corporate directory.

**Configuration steps:**
i. Navigate to the **sonar.properties** configuration file.
ii. Enable and configure LDAP settings like:
   ```properties
   sonar.security.realm=LDAP
   ldap.url=ldap://localhost:389
   ldap.bindDn=cn=admin,dc=example,dc=com
   ldap.bindPassword=admin
   ldap.user.baseDn=ou=Users,dc=example,dc=com
   ldap.group.baseDn=ou=Groups,dc=example,dc=com
   ```
iii. Restart SonarQube for the changes to take effect.

### 2 OAuth2 Authentication
SonarQube supports OAuth2 authentication, allowing users to log in using third-party identity providers such as:
- **Google**
- **GitHub**
- **GitLab**
- **Azure Active Directory**

This method leverages **OAuth2**, which simplifies authentication by delegating the process to trusted third-party providers, reducing the need to manage credentials within SonarQube itself.

**Example configuration for GitHub:**
1. Go to **Administration** -> **Security** -> **Authentication**.
2. Configure the **Client ID** and **Client Secret** from GitHub OAuth app settings.
3. Enable **Login with GitHub** for seamless login integration.

---

## Token-Based Authentication

### Personal Access Tokens (PAT)
SonarQube supports token-based authentication, allowing users to generate **Personal Access Tokens (PATs)** for secure interaction with the API.

**Use Cases:**
- Automating interactions with SonarQube (e.g., triggering scans, managing settings).
- Integrating SonarQube analysis into CI/CD pipelines without exposing credentials.

**How to create a token:**
1. Log in to SonarQube.
2. Go to the user's **Account Settings** -> **Security**.
3. Create a new token by giving it a name and defining the necessary permissions.

The generated token can then be used in API calls or in CI tools like Jenkins, CircleCI, etc.

---

## SAML Authentication

### Single Sign-On (SSO) with SAML 2.0
For enterprise-grade authentication, SonarQube supports **SAML 2.0**. This allows integration with **Identity Providers (IdP)** like **Okta**, **Keycloak**, or **Azure AD**, enabling Single Sign-On (SSO) for users.

**Benefits:**
- SSO reduces the need to manage separate credentials for SonarQube.
- Enhanced security through multi-factor authentication (MFA) enforced by the IdP.

**Steps to configure SAML authentication:**
i. Navigate to **Administration** -> **Security** -> **Authentication**.
ii. Select **SAML Authentication** and configure the following:
   - **SAML login URL** (from your IdP).
   - **SAML logout URL**.
   - **X.509 certificate** from the IdP for signature validation.
iii. Test the SSO login and ensure successful integration.

---

## Security Best Practices

### 1 Enforce Strong Password Policies
For built-in authentication, ensure that users follow strong password policies, including:
- Minimum length.
- Use of special characters, numbers, and uppercase letters.
- Regular password expiration.

### 2 Enforce MFA (Multi-Factor Authentication)
Wherever possible, use external authentication providers that enforce **MFA** for an additional layer of security.

### 3 Restrict Access via IP Whitelisting
To add an extra layer of security, administrators can restrict access to the SonarQube server based on specific IP ranges, especially if it is publicly exposed.

---

## Conclusion

SonarQube provides flexible authentication mechanisms, from local user management to enterprise-level integrations such as LDAP, OAuth2, and SAML. Each method enhances security and simplifies the login process based on the organization’s needs. By implementing proper authentication measures, organizations can ensure that their code quality data and project integrity remain protected. the recommended authentication method is SonarQube's built-in authentication due to its simplicity and ease of setup. It allows for quick user and group management without the need for complex external integrations like LDAP or OAuth2, making it ideal for smaller teams. 


## Contact Information 
|Name|Email Address|
|:---:|:---:|
|Aayush|aayush.gaur.snaatak@mygurukulam.co|

## References 
|links | Description |
|-------| -------------|
| https://docs.sonarsource.com/sonarqube/latest/instance-administration/security/ | SonarQube Security |

---

