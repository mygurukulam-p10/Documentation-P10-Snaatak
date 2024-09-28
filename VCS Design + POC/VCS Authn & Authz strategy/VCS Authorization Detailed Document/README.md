# VCS Authorization Detailed Document

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
|Abhinav Singh| 18-09-24    | Version 1  | Abhinav Singh   | 22-09-24       |

![image](https://github.com/user-attachments/assets/30c3847f-047d-45c1-9a02-c76be5406941)

VCS uses various strategies to manage repository access. This guide explains authorization methods in Git, their configuration, and best practices to secure permissions, ensuring only authorized users can modify your repositories.

## Table of Contents
1. [Introduction](#introduction)
2. [Why we need Authorization](#why-we-need-authorization)
3. [Access levels in VCS Authorization](#access-levels-in-vcs-authorization)
4. [Audit trails in VCS authorization](#audit-trails-in-vcs-authorization)
5. [Conclusion](#conclusion)
6. [Contact Information](#contact-information)
7. [References](#references)


## Introduction

Authorization in Version Control Systems (VCS) controls user permissions, ensuring only authorized actions like reading, writing, or managing repositories. Common strategies include role-based access, branch protection, and pull request approvals, safeguarding the codebase by restricting critical changes to trusted users.

## Why we need Authorization

|    Reason    |    Explaination    |
|--------------|--------------------|
| **Security** | Protects the codebase from unauthorized changes. |
| **Integrity** | Maintains code quality by controlling who can make updates. |
| **Accountability** | Tracks who makes changes for auditing.|
| **Compliance** | Ensures access aligns with policies and regulations. |
| **Collaboration** | Facilitates teamwork with appropriate access levels. |



## Access levels in VCS authorization

|    Levels    |    Description    |
|--------------|--------------------|
| **Read-Only** | View and clone repositories. |
| **Write-Access** | Push changes and create branches.|
| **Admin** | Full control and configuration. |
| **Triage** | Manage issues and pull requests without write access to code.. |
| **Guest** | Limited, often read-only access. |



## Audit trails in VCS authorization

|    Audit Trail    |    Description    |
|--------------|--------------------|
| **Commits** | Records who made changes and what was changed. |
| **Pull Requests** | Tracks review and merge history.|
| **Access Changes** | Logs modifications to user permissions and roles. |
| **Branch Actions** | Tracks branch creation, deletion, and modifications of branches. |

## Conclusion

Effective VCS authorization is vital for securing code repositories and ensuring proper access control. By using strategies such as role-based access, branch protection, and pull request approvals, along with integration with identity providers, organizations can manage permissions, maintain code integrity, and support collaboration while ensuring compliance and accountability.

## Contact Information
For more information, feedback, or assistance, feel free to contact:
| Name                   | Email address          |
|------------------------|------------------------|
| Abhinav Singh          | abhinav.singh.snaatak@mygurukulam.co  |


## References

| Links                                             | Descriptions                           |
|---------------------------------------------------|----------------------------------------|
| https://docs.gitlab.com/ee/user/permissions.html  | Permissions and Roles in Gitlab|
| https://docs.github.com/en/get-started/learning-about-github/access-permissions-on-github | Access Permissions on Github |


