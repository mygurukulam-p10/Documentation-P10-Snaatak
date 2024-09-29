# VCS Authorization Setup

|  Author        | Created on |  Version  | Last updated by  | Last edited on |
|----------------|------------|-----------|------------------|----------------|
| Abhinav Singh  |   25-09-24 | version 1 |   Abhinav Singh  |     28-09-24   |
  
## Table of Contents

1. [Purpose](#purpose)
2. [System Prerequisites](#system-prerequisites)
3. [Creating Organisation and Adding Contributers](#Creating-organisation-and-adding-contributers)
4. [Assigning Roles to the users](#assigning-roles-to-the-users)
5. [Protecting Critical Branches in GitHub](#protecting-critical-branches-in-github)
6. [Conclusion](#conclusion)
7. [Contact Information](#contact-information)
8. [References](#references)

## Purpose
Authorization in version control systems (VCS) ensures that only users with the appropriate permissions can modify or manage resources within a repository. This guide explains the various methods of authorization in Git-based systems (GitHub, GitLab, Bitbucket), how to configure them, and best practices for maintaining secure access control to your repositories.


## System Prerequisites

| Requirements         | Description                |
|----------------------|-------------------------------|
|    GitHub Account     |   To create Organisation  |
| Git Version           | 2.28 or higher                |
| Admin or Maintainer Access | Required to manage roles and permissions |
| Branch Policies       | Enforced for critical branches like `main` |

## Creating Organisation and Adding Contributers

**1. In your profile Section choose Your organisations**

![image](https://github.com/user-attachments/assets/f5e3acfe-2d5b-495a-95c6-2cc2743aa49d)

**2. In the right corner of the page Choose New organisation**

![image](https://github.com/user-attachments/assets/50ad0e87-8f06-406d-b90c-287baa0bddd3)

**3. Pick a plan for your organization** 

![image](https://github.com/user-attachments/assets/4f032712-aa7d-40a6-9be8-66f89a9ac75e)

**4. Provide details about your organisation and choose Next**

![image](https://github.com/user-attachments/assets/db780aa6-6606-4490-bcc8-26197820ed2d)

**5. Add members to your Organisation and complete setup**.

![image](https://github.com/user-attachments/assets/fa0ec22c-07c5-462b-9201-441da7573705)

**6. You can add users to the organisation later also by sending invites.**

![image](https://github.com/user-attachments/assets/240d94b1-da56-4fbc-9006-e405151c97d9)

**8. We can create teams for different groups.**

![image](https://github.com/user-attachments/assets/c3b62744-014d-4185-ad4d-8a62066ffe4b)

**9. We can add users or collaborators to a team using "Add a member" icon in the team.**

![image](https://github.com/user-attachments/assets/20479523-05ba-4b8b-9aa0-75afe72c029a)


## Assigning Roles to the users

**1. Choose the user you want to assign Permissions.**

![image](https://github.com/user-attachments/assets/1ed4a5f2-86fd-4233-9f80-0e4a90756573)

**2. Choose Manage access** 

![image](https://github.com/user-attachments/assets/4cb51e1d-0804-4e03-a15b-393f6d37bb63)


**3. We can edit privilages of the user and provide required permission**

![image](https://github.com/user-attachments/assets/b9ae0197-47e1-4f6a-b6fd-da7f9e21c3fe)

![image](https://github.com/user-attachments/assets/ae3b052e-15e5-42f6-93e7-df138db4c5e8)


## Protecting Critical Branches in GitHub

**1. Navigate to Repository Settings**

![image](https://github.com/user-attachments/assets/f10e220c-4813-4c49-addc-794fda11022a)

**2. In the left sidebar, click on "Branches"**

**Click on Rules and then Ruleset to create a New Ruleset**
  
![image](https://github.com/user-attachments/assets/9cbd88d1-4d4c-4dc1-a03b-3fc97e9d05ff)

**3. Choose New Branch Ruleset**

![image](https://github.com/user-attachments/assets/278f5b05-5cd3-49ac-aab6-2a593e429325)


**4. Choose name and assign rules as per requirement**

![image](https://github.com/user-attachments/assets/8bc5fcd4-e65a-44e5-b8f4-23416c37c163)


![image](https://github.com/user-attachments/assets/c18d6960-7aa5-4f26-8d8f-6e7dbae1665c)



## Conclusion

Effective VCS authorization is essential for safeguarding your codebase. By implementing role-based access, branch protection, and pull request reviews, you can ensure secure and controlled access, fostering collaboration while maintaining code integrity.

## Contact Information

For more information, feedback, or assistance, feel free to contact:

| Name                   | Email address          |
|------------------------|------------------------|
| Abhinav Singh          | abhinav.singh.snaatak@mygurukulam.co  |


## References

| Links                                             | Descriptions                           |
|---------------------------------------------------|----------------------------------------|
| https://docs.gitlab.com/ee/user/permissions.html  | Permissions and Roles in Gitlab|
| https://tinyurl.com/4cnja8ph | Access Permissions on Github |
