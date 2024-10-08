## Pre-existing IAM Policies
![Screenshot from 2024-10-08 06-00-47](https://github.com/user-attachments/assets/a42922aa-17b9-4c06-af6b-451bd9ce051b)


***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Aayush Gaur| 08-10-2024 | Aayush Gaur | 08-10-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why Pre-existing IAM Policies ](#WhyPre-existingIAMPolicies)
+ [Features Pre-existing IAM Policies ](#FeaturesPre-existingIAMPolicies)
+ [ Pre-existing IAM Policies Best Practices](#Pre-existingIAMPoliciesBestPractices)
+ [Advantages](#Advantages)
+ [Disadvantages](#Disadvantages)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction
Identifying existing IAM (Identity and Access Management) policies is an important step in securely managing access to AWS (Amazon Web Services) resources. These policies specify the permissions given to users, groups, or roles within AWS. By using pre-built IAM policies, organizations can make managing access easier, follow security best practices, and meet regulatory standards.

***
## Why Identify Pre-existing IAM Policies
Identifying and using pre-existing IAM policies in AWS helps organizations take advantage of already set up access controls and best practices. This reduces the need to create new policies from scratch, keeps things consistent, and makes managing access easier. By using these existing policies, organizations can quickly set up secure access, avoid mistakes in configurations, and strengthen the security of their AWS environment.

****
## Features of Pre-existing IAM Policies
| **Feature**             | **Description**                                                                                           |
|-------------------------|-----------------------------------------------------------------------------------------------------------|
| **Granular Permissions** | These policies give you very specific control over what users can do in AWS. You can decide exactly which actions they are allowed to take and what resources they can access. |
| **Predefined Best Practices**          | These policies follow AWS security guidelines, helping you avoid common mistakes and keep your setup safe. |
| **Flexibility**          | Pre-existing IAM policies provide flexibility to accommodate diverse use cases and requirements, ensuring that access controls align with organizational needs. |
| **Scalability** | As your AWS usage grows, these pre-made policies make it easy to manage permissions for more users and services without much extra effort. |
| **Time Efficiency**      | Using pre-existing policies saves time as they eliminate the need for creating policies from scratch for common access control scenarios. |
| **Consistency**          | Pre-existing policies help ensure consistency across environments by offering standardized access controls. |
| **Least Privilege**      | Many pre-existing policies are designed with the principle of least privilege, granting only the necessary permissions for specific tasks. |
| **Simplified Management**| Centralized and easy-to-manage policies reduce administrative overhead while ensuring secure access management. |



## Advantages of Identifying Pre-existing IAM Policies
| **Advantage**                 | **Explanation**                                                                                     |
|-------------------------------|-----------------------------------------------------------------------------------------------------|
| **Easy to Use**                | Pre-existing policies are ready-made, so you don't have to create them from scratch, saving time.    |
| **Secure**                     | They are built with security in mind, following AWS best practices to keep your resources safe.      |
| **Saves Time**                 | These policies are quick to apply, helping you set permissions without spending a lot of time.       |
| **Consistency**                | Using the same policies across your environment ensures that permissions are handled the same way everywhere. |
| **Reduces Mistakes**           | Because the policies are pre-made, there’s less chance of making errors compared to creating custom policies. |

***
## Disadvantages of Identifying Pre-existing IAM Policies
| **Disadvantage**            | **Description**                                                                                       |
|-----------------------------|-------------------------------------------------------------------------------------------------------|
| **Limitations**             | Pre-existing IAM policies might not fit exactly with what your organization needs. You may need to tweak them or create additional policies to meet your specific requirements. |
| **Complexity**              | If you have many pre-existing policies, it can get complicated to manage them all. You need to stay organized, keep good documentation, and regularly check that everything is working correctly. |


***
## Pre-existing IAM Policies
### Step1: Specify user details
![Screenshot from 2024-10-08 06-20-24](https://github.com/user-attachments/assets/3f3f7387-e013-4b27-9590-67aae629af74)


***
### step2: Explore The Policies & Attach As Per Requirement
![Screenshot from 2024-10-08 06-22-38](https://github.com/user-attachments/assets/42e417a7-601f-41b2-b41c-dc1051265186)

![Screenshot from 2024-10-08 06-23-58](https://github.com/user-attachments/assets/3a0a6270-6487-4b10-86d7-d0d8d4ed4dad)


***
### Step3: Review and create
![Screenshot from 2024-10-08 06-25-21](https://github.com/user-attachments/assets/6a24b6cf-bae2-4b5c-9c04-7510bb606e26)
![Screenshot from 2024-10-08 06-26-49](https://github.com/user-attachments/assets/063f3ca1-c9fe-43e7-8889-bea3cd8a0a9b)

***

## Best Practices
| **IAM Policy**                           | **Description**                                                             | **Best Practices**                                                                                  |
|------------------------------------------|-----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **AmazonEC2FullAccess**                  | Gives full access to manage Amazon EC2 instances and resources.              | Use for administrators who need to manage EC2 instances and related resources.                       |
| **AWSLambdaFullAccess**                  | Grants full access to AWS Lambda functions and resources.                   | Assign to developers managing Lambda, but avoid giving it to users who don’t need full control.      |
| **AmazonS3FullAccess**                   | Provides full access to Amazon S3 buckets and objects.                      | Limit this to users who actually need full control over S3, and avoid unnecessary access.            |
| **IAMUserChangePassword**                | Lets IAM users change their own passwords.                                  | Enable this only for users who need to change their own passwords.                                   |
| **AWSManagedAdministratorAccess**        | Provides full administrative access to all AWS services and resources.       | Use cautiously and only give to trusted administrators due to the high level of access.              |
| **AmazonRDSFullAccess**                  | Grants full access to manage Amazon RDS resources.                          | Restrict this to users who need to manage databases to avoid unneeded access.                        |
| **AmazonDynamoDBFullAccess**             | Full control over Amazon DynamoDB tables and resources.                     | Assign to those managing DynamoDB resources, and ensure it's only given to necessary users.          |
| **ReadOnlyAccess**                       | Provides read-only access to all AWS services and resources.                | Ideal for auditors or users who only need to view resources, not modify them.                        |
| **AWSCodeDeployFullAccess**              | Grants full access to AWS CodeDeploy resources.                             | Limit this to users responsible for managing deployments.                                            |
| **AmazonVPCFullAccess**                  | Full access to Amazon Virtual Private Cloud (VPC) resources.                | Assign to network administrators handling VPC configurations.                                        |
| **IAMSelfManageServiceSpecificCreds**     | Allows IAM users to manage their own service-specific credentials.           | Only enable this for users who need temporary access credentials to manage services.                 |

***

## Conclusion
Identifying pre-existing IAM policies is a strategic approach to access management in AWS environments, offering efficiency, consistency, and compliance benefits. While pre-existing policies streamline access control implementation and promote security best practices, organizations must also address challenges such as policy limitations and complexity. By leveraging pre-existing IAM policies effectively and supplementing them as needed, organizations can establish robust access controls that align with their security objectives and regulatory obligations within AWS environments.

***
## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Aayush Gaur   | aayush.gaur.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://deliciousbrains.com/wp-offload-media/doc/custom-iam-policy-for-amazon-s3/|
| Link | https://docs.aws.amazon.com/iam/ |

