# SonarQube Authentication & Authorization

| Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Aayush Gaur | 24-09-24 | version 1 | Aayush Gaur | Intial Commit |

## Table of Contents
- [Introduction](#introduction)

## 1. Introduction to SonarQube Authentication (authn) & Authorization (authz)

**Authentication (authn)** and **Authorization (authz)** are crucial for managing and securing access to SonarQube, ensuring that only authorized users can interact with the system and defining the level of access they have.

- **Authentication (authn)**: The process of verifying the identity of a user trying to access SonarQube.
- **Authorization (authz)**: The process of determining what an authenticated user is allowed to do within the SonarQube system.

---

## 2. SonarQube Authentication Methods

SonarQube provides multiple ways to authenticate users, including built-in authentication as well as integration with external identity providers for single sign-on (SSO).

### a. Built-in Authentication (Local Authentication)

SonarQube includes a built-in user management system where users can be authenticated using a username and password stored in the SonarQube database. 

- **Default Admin User**: SonarQube comes with a default admin user (`admin/admin`) for the initial login. This should be changed immediately for security reasons.
- **User Management**: Administrators can create, delete, or update users, and assign passwords directly within SonarQube.

### b. External Authentication Systems

SonarQube supports external authentication systems, which allow users to log in using credentials managed outside of SonarQube.

#### i. LDAP/Active Directory (AD)

- **LDAP Integration**: SonarQube can authenticate users against an LDAP or Active Directory server.
- **LDAP Configuration**: Administrators must configure LDAP properties in the SonarQube configuration file (`sonar.properties`) to connect with the LDAP/AD server.

#### ii. Single Sign-On (SSO)

- **SAML Authentication**: Security Assertion Markup Language (SAML) allows users to authenticate with SonarQube using corporate identity providers.
- **OAuth2/OpenID Connect**: SonarQube can integrate with OAuth2 or OpenID Connect providers like GitHub, Google, or Microsoft for user authentication.
- **JWT (JSON Web Tokens)**: SonarQube can accept JWT tokens for users authenticated by external systems.

#### iii. GitHub and GitLab Login

SonarQube integrates with GitHub and GitLab for authentication, allowing developers to log in using their GitHub or GitLab credentials.

---

## 3. SonarQube Authorization Methods

Authorization in SonarQube determines what actions a user can perform once authenticated. SonarQube uses a role-based access control (RBAC) model, where users are assigned to groups, and groups are granted permissions.

### a. Built-in Roles

SonarQube has several predefined roles that simplify access management:

- **Admin**: Full access to SonarQube, including managing projects, users, and system settings.
- **Code Viewer**: Can view code and see all project details but cannot modify them.
- **Security Reviewer**: Can see security reports and issues in the code but may not have full admin privileges.
- **User**: Has access to general project information but cannot see sensitive information or make system-wide changes.

### b. Custom Roles and Groups

Administrators can create custom roles and assign users to these roles to have more granular control over access. Permissions can be set per project or globally.

### c. Permission Templates

SonarQube allows administrators to define **Permission Templates**. These templates assign default permissions to users for new projects.

### d. Project-Level Authorization

SonarQube also allows configuring authorization at the project level:

- **Project Visibility**: Projects can be made public or private.
- **Granular Permissions**: Specific permissions such as code viewing, analysis execution, or admin rights can be assigned at the project level.

---

## 4. Authentication and Authorization Configuration in SonarQube
