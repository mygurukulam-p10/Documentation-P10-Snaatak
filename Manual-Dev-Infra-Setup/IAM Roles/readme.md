## Create IAM Role
![image](https://github.com/avengers-p7/Documentation/assets/156056746/2c667c75-38b7-4758-b009-1d38fa556a86)

***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Aayush Gaur| 08-10-2024 | Aayush Gaur | 08-10-2024|
***
## Table of Contents
+ [Introduction to C](#Introduction-to-iam-role)
+  [Why IAM Role](#Why-iam-role)
+ [Features of to IAM Role](#Features-of-iam-role)
+ [Types of IAM Role in aws](#TypesofIAMRoleinaws)
+ [Advantages of IAM Role](#Advantages-of-iam-role)
+ [Disadvantages of IAM Role](#Disadvantages-of-iam-role)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [Resources and References](#Resources-and-References)

***
## Introduction to IAM Role
IAM (Identity and Access Management) roles in AWS (Amazon Web Services) help you control who can access your AWS resources, like databases or servers, in a safe way. Instead of giving out passwords or access keys that last a long time, IAM roles let you give temporary access to people, apps, or AWS services when they need it. This makes managing access more flexible and secure, as permissions can be given only when needed, without risking sensitive information.

***
## Why IAM Role
IAM roles are created to securely give temporary access to AWS resources without attaching long-term credentials to specific people. Instead of assigning permissions directly to users, roles allow different entities—such as AWS services, applications, or users—to take on temporary permissions when they need them. This helps organizations follow the "least privilege" rule, which means giving only the necessary access for specific tasks. Using roles makes things safer by lowering the risk of exposing sensitive credentials and preventing unauthorized access.

***
## Features of IAM Role
| Feature                   | Description |
|---------------------------|-------------|
| **Granular Permissions**   | IAM roles let you define specific permissions for what actions can be performed and on which resources. This ensures that entities only have access to what they really need. |
| **Temporary Credentials**  | When an IAM role is assumed, it issues temporary security credentials that expire after a set time, reducing the chances of long-term credential exposure. |
| **Cross-Account Access**   | IAM roles make it easy to securely share resources across different AWS accounts, allowing teams to collaborate while keeping security in check. |
| **No Permanent Association** | Unlike IAM users, roles aren't tied to a specific user. Any trusted entity—like an AWS service or application—can assume a role when needed. |
| **Federated Access**       | IAM roles allow external users (from identity providers like Google) to access AWS resources temporarily, without creating IAM users for them. |

***

***
## Types of IAM Role in aws
| Role Type                   | Description |
|-----------------------------|-------------|
| **EC2 Instance Roles**       | EC2 instance roles (IAM roles) grant permissions to applications running on EC2 instances. These roles allow EC2 to interact with AWS services without needing to manage access keys directly. |
| **Lambda Execution Roles**   | Lambda execution roles are used by AWS Lambda functions to access other AWS resources, defining what the function can do when it runs. |
| **Cross-Account Roles**      | Cross-account roles let IAM users from one AWS account access resources in another account. These are often used for resource sharing across multiple accounts securely. |
| **Service Roles**            | Service roles are assigned to AWS services like Lambda, EC2, or RDS to perform actions on your behalf. They allow services to interact with AWS resources automatically. |
| **IAM Roles**                | IAM roles delegate permissions to entities like AWS services, users, or federated identities, helping in scenarios like cross-account access or allowing applications to access resources. |
| **ECS Task Execution Roles** | ECS task execution roles are used by Amazon ECS tasks to access AWS services like S3, defining the permissions for tasks during execution. |
| **S3 Bucket Access Roles**   | S3 bucket access roles provide cross-account access to Amazon S3 buckets, enabling different accounts to securely access specific buckets for shared use cases. |
| **EC2 Instance Profile Roles** | EC2 instance profile roles are specific to EC2 instances and help manage permissions for applications running on them, similar to EC2 instance roles but dedicated to the instance profiles. |


***

## Advantages of IAM Role
| Advantage                 | Description |
|---------------------------|-------------|
| **Temporary Access**       | IAM roles provide temporary security credentials, which makes access safer by reducing the risk of long-term exposure. |
| **No Hard-Coded Credentials** | You don't need to store access keys in your code or applications, reducing the risk of accidental leaks. |
| **Flexible Permissions**   | Roles allow you to assign permissions dynamically, making it easier to grant specific access when needed. |
| **Cross-Account Access**   | You can easily share resources between different AWS accounts securely without creating separate users. |
| **Service Integration**    | IAM roles integrate with many AWS services, allowing them to securely access resources on your behalf. |
| **Least Privilege**        | Roles help you enforce the principle of least privilege by giving just the necessary permissions for each task. |

***
## Disadvantages of IAM Role
| Disadvantage               | Description |
|---------------------------|-------------|
| **Complex Management**      | Managing multiple IAM roles and their permissions can become complicated, especially in large environments. |
| **Trust Relationship Configuration** | Setting up trust relationships for cross-account access can be tricky and may introduce security risks if not done correctly. |
| **Limited Permissions Visibility** | It can be difficult to track which roles have been granted permissions and to whom, leading to potential oversight. |
| **Potential Misconfiguration** | Misconfiguring a role can result in excessive permissions, exposing resources to unauthorized access. |
| **Dependency on AWS Services** | Some roles are dependent on AWS services, meaning if those services have issues, it could impact the functionality of your applications. |


***

## Steps to Create IAM Role

### Step 1: Search IAM in the search section and click on it to navigate to IAM 
![Screenshot from 2024-10-08 19-55-17](https://github.com/user-attachments/assets/c8c8d889-ee13-4726-bfaa-be882af75673)

### Step 2: Access the IAM Roles Section
![Screenshot from 2024-10-08 19-57-41](https://github.com/user-attachments/assets/0be72506-8b52-4cb7-bff1-7731ea4aa445)

### Step 3: 


