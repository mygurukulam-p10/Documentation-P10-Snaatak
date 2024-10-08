##  IAM Users and Groups
![Screenshot from 2024-10-08 06-00-47](https://github.com/user-attachments/assets/6ae4b754-5700-4fec-9e5b-d0bb99ed3a20)


***

| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Aayush Gaur| 08-10-2024 | Aayush Gaur | 08-10-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+ [ Why Create IAM Users and Groups](#WhyCreateIAMUsersandGroups)
+ [ Features of IAM Users and Groups](#FeaturesofIAMUsersandGroups)
+ [Advantages of IAM Users and Groups](#AdvantagesofIAMUsersandGroups)
+ [Disadvantages of IAM Users and Groups](#DisadvantagesofIAMUsersandGroups)
+  [IAM Users and Groups add best practices ](#IAMUsersandGroupsaddbestpractices )
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
IAM (Identity and Access Management) users and groups are key parts of AWS (Amazon Web Services) security. They help you control who can access your AWS resources. An IAM user is like an individual person (such as an employee or an application) that uses AWS services. IAM groups are collections of users who need similar permissions. By creating IAM users and groups, companies can enforce security rules, control who has access to what, and stay compliant with security requirements.

***
## Why Create IAM Users and Groups
Creating IAM users and groups is important for keeping AWS accounts secure. By giving each user their own login details and permissions, and by organizing them into groups based on their roles or tasks, you can make sure everyone only has the access they need to do their job (following the “least privilege” rule). It also makes managing access easier, as you can control permissions for many users at once, and keep track of what people are doing in AWS for audits or reviews.

***
## Features of IAM Users and Groups

| **Feature**                  | **Description**                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| **Granular Access Control**   | You can give users very specific permissions, deciding exactly what actions they are allowed to perform on AWS resources. |
| **Role-Based Access**         | You can group users who need similar access and assign them the right permissions at once, making it easier to manage.   |
| **Centralized Management**    | Managing users and permissions is simpler because everything is organized in one place, ensuring consistent security for your AWS environment. |
| **Easier Permission Updates** | When you need to change access for a group of users, you can update their permissions in one step instead of doing it for each user individually. |
| **Improved Security**         | By grouping users and controlling what they can access, you reduce the risk of giving too much access, keeping your environment more secure. |


***

## Advantages of IAM Users and Groups
| Advantage |	Description |
|-----------|-------------|
| **Enhanced Security**	| IAM users and groups enable organizations to enforce the principle of least privilege, reducing the risk of unauthorized access and potential security breaches.|
| **Scalability** | 	With IAM users and groups, organizations can easily scale access control mechanisms as their AWS infrastructure grows, accommodating changes in user roles or resource requirements.|
| **Simplified Administration**	| Centralized management of IAM users and groups streamlines administration tasks, such as provisioning and deprovisioning access, minimizing administrative overhead.|

***
## Disadvantages of IAM Users and Groups
| Disadvantage	| Description |
|---------------|-------------|
| **Complexity**	| Managing a large number of IAM users and groups can introduce complexity, requiring careful organization and documentation to ensure effective access control. |
| **Potential for Misconfiguration** |	Incorrectly configured IAM policies or group memberships can result in unintended access restrictions or security vulnerabilities, necessitating thorough testing and regular review.|

***

***
### How to create your first IAM user and user group
![image](https://github.com/avengers-p7/Documentation/assets/156056746/1361ef75-84a7-4a07-935e-9ea77ff166aa)

***
### Navigate to AWS Services and search for IAM to access the IAM console.
![image](https://github.com/avengers-p7/Documentation/assets/156056746/3e256943-917a-4af7-821f-af8ba4ea6267)

***
###  From the IAM console select Users on the left-handside and click Add Users
![image](https://github.com/avengers-p7/Documentation/assets/156056746/20dc7c1c-263d-4c27-a250-bada6be0824d)

***
 **Under User name type 'Administrator'**

 **Check the box: Password - AWS Management Console access**

 **create a custom password & create**

 **Click: permissions**
![Screenshot from 2024-10-08 04-52-58](https://github.com/user-attachments/assets/4cb3765a-45f7-4b44-933e-abc5a1c770d0)

 ***
 ## Navigate to Users and click 'Add permissions'
![Screenshot from 2024-10-08 04-56-18](https://github.com/user-attachments/assets/67d3be21-d376-44cb-bea2-92fa4ebac203)

 ![Screenshot from 2024-10-08 04-55-05](https://github.com/user-attachments/assets/1859345d-cf72-4a82-8a32-683aeade0b39)


 ***
 ## Create the group and add user in the group
**Name the group - Dev**

**Add user in the group**

**Attach policies and then click "Create group"**
 
![Screenshot from 2024-10-08 05-03-13](https://github.com/user-attachments/assets/543b8d7e-a136-48bb-bc0a-43c417141a15)


***
## After creating the group, now you can see the group in 'Users group' section.
![Screenshot from 2024-10-08 05-06-01](https://github.com/user-attachments/assets/0ff88d3a-acf6-464b-85ff-e041b86514a6)


***
## Under the Dev group 'User 1' is attached with Ec2 full access 
![Screenshot from 2024-10-08 05-24-19](https://github.com/user-attachments/assets/1cd6d137-058c-4b4c-8bc7-6df427514743)


***

## IAM Users and Groups add best practices 
| **Best Practice**                  | **Explanation**                                                                                          |
|------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Follow Least Privilege Principle**| Give users only the permissions they need to do their job, nothing more. This keeps your AWS environment safer. |
| **Use Groups for Permissions**     | Instead of assigning permissions to each user, put users in groups and give permissions to the group. It makes managing permissions easier. |
| **Enable Multi-Factor Authentication (MFA)** | Add an extra layer of security by requiring users to use MFA, which requires a second form of authentication, like a code from a mobile app. |
| **Rotate Credentials Regularly**   | Change passwords and access keys frequently to reduce the risk of unauthorized access.                    |
| **Use Strong Password Policies**   | Require users to create strong, complex passwords (e.g., with numbers, symbols, and capital letters) to improve security. |
| **Don’t Share Credentials**        | Each user should have their own login and not share usernames or passwords. This keeps accounts more secure and easier to track. |
| **Review and Remove Unnecessary Permissions** | Regularly check what permissions users have and remove any that are not needed anymore.                   |
| **Monitor User Activity**          | Keep track of what users are doing by enabling logging. This helps you spot any unusual activity or potential security risks. |


## Conclusion
AM users and groups are key parts of AWS security that help organizations control who can access their AWS resources and what they can do. By setting up clear user permissions, businesses can keep their data safe and make sure they follow security rules. While IAM provides strong security and can easily grow with your needs, it can sometimes feel complex, and mistakes can happen if not managed carefully. Overall, IAM users and groups are important for protecting AWS resources, and using them correctly helps maintain a secure and organized environment. It’s also crucial to regularly review and update permissions to ensure everything stays secure as your needs change.

***


## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Aayush Gaur   | aayush.gaur.snaatak@mygurukulam.co |

***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://dev.to/aws-builders/creating-your-first-iam-admin-user-and-user-group-in-your-aws-account-machine-learning-part-1-3cne|
