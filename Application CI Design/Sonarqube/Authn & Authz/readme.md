# SonarQube Authentication & Authorization

| Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Aayush Gaur | 24-09-24 | version 1 | Aayush Gaur | Intial Commit |

## Table of Contents
- [Introduction](#introduction)

### Introduction
Authentication (authn) and Authorization (authz) are crucial for managing and securing access to SonarQube, ensuring that only authorized users can interact with the system and defining the level of access they have.

- **Authentication (authn)**: The process of verifying the identity of a user trying to access SonarQube.
- **Authorization (authz)**: The process of determining what an authenticated user is allowed to do within the SonarQube system.

### SonarQube Authentication Methods
SonarQube provides multiple ways to authenticate users. These include built-in authentication as well as integration with external identity providers for single sign-on (SSO). Some common methods:

**1. Built-in Authentication (Local Authentication)**
SonarQube includes a built-in user management system where users can be authenticated using a username and password stored in the SonarQube database. This is typically used in smaller or standalone deployments.

- **Default Admin User**: SonarQube comes with a default admin user (admin/admin) for the initial login. This should be changed immediately for security reasons.
- **User Management**: Administrators can create, delete, or update users, and assign passwords directly within SonarQube.

**2. External Authentication Systems**
SonarQube supports external authentication systems, which allow users to log in using credentials managed outside of SonarQube. These systems typically enhance security, offer better scalability, and allow centralized user management.

**a. LDAP/Active Directory (AD)**
- **LDAP Integration**: SonarQube can authenticate users against an LDAP or Active Directory server. This integration ensures that users are verified using corporate credentials.
- **LDAP Configuration**: Administrators must configure LDAP properties in the SonarQube configuration file (sonar.properties) to connect with the LDAP/AD server.


