## Create Custom IAM Policies


***
| Author | Created on | Last updated by | Last edited on |
|--------|------------|-----------------|----------------|
|Aayush Gaur| 09-10-2024 | Aayush Gaur| 09-10-2024|

***
## Table of Contents
+ [Introduction](#Introduction)
+  [Why Custom IAM Policies](#why-custom-iam-policies)
+ [Features Custom IAM Policies ](#features-custom-iam-policies)
+ [Advantages of Custom IAM Policies](#advantages-of-custom-iam-policies)
+ [Disadvantages of Custom IAM Policies](#disadvantages-of-custom-iam-policies)
+ [ Create Custom IAM Policies](#create-custom-iam-policies)
+  [Custom IAM Policies best practices](#Custom-iam-policies-best-practices)
+ [Conclusion](#Conclusion)
+ [Contact Information](#contact-information)
+ [Resources and References](#resources-and-references)

***
## Introduction
Custom IAM (Identity and Access Management) policies let organizations control who can access which AWS resources in a way that fits their unique needs. While AWS offers some ready-made policies, custom IAM policies give more flexibility. With them, you can decide exactly what actions users can or cannot do, and you can also set specific conditions for these permissions to suit your organization's requirements.

***
## Why Create custom IAM policies
Creating custom IAM policies allows you to have precise control over who can do what in your AWS account. Here's why you'd want to create them:

- **Tailored Access**: Every organization has different needs. Custom IAM policies let you define exactly what access each user or service needs, rather than using AWS's predefined policies, which may be too broad or too narrow.
- **Better Security**: You can restrict access to only the actions and resources people actually need, reducing the risk of accidental changes or security breaches.
- **Specific Conditions**: You can set conditions, like time of day or specific IP addresses, under which certain actions are allowed, giving even more control over access.
- **Flexibility**: Custom policies let you adapt as your organization grows or changes, ensuring the right people have the right access at all times.

***
## Features of Custom IAM Policies
| Feature | Description |
|---------|-------------|
| **Conditional Access** | Custom policies let you set conditions, like time, location, or specific tags on resources, to control when and how users can access AWS services, adding extra security and flexibility. |
| **Granular Control** | You can define specific permissions with custom IAM policies, giving precise control over what actions a user or role can take on your AWS resources. |
| **Integration with AWS Services** | These custom policies work smoothly with different AWS services, like IAM roles, S3 buckets, Lambda functions, and more, making access management easier. |
| **Versioning and Rollback** | IAM policies allow you to keep track of changes by saving multiple versions, so you can easily go back to an earlier version if needed. This helps maintain better control over policy updates. |
| **Audit and Monitoring** | Custom IAM policies can be monitored through AWS CloudTrail, which helps track policy usage and ensures that users are following the rules set by the organization. |


***

##  Advantages of Custom IAM Policies
| Advantages                       | Description                                                                                                                             |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| **Enhanced Security**         | Custom policies allow you to set specific conditions (like IP address or time), adding extra security and reducing the risk of breaches.|
| **Flexibility and Scalability**| As your business grows, custom policies can be easily adjusted to meet new needs and scale as your AWS resources expand.                |
| **Least Privilege Principle** | Custom policies make sure users only get the permissions they really need, which improves security by minimizing unnecessary access.    |
| **Tailored Access Control**   | You can create policies that fit your exact security and compliance needs, ensuring people only access what they should.                |
| **Better Control and Management**| Custom policies provide better control, making it easier to manage and review access permissions regularly for optimal security.       |


***

## Disadvantages of Custom IAM Policies

| Disadvantages                   | Description                                                                                           |
|----------------------------------|-------------------------------------------------------------------------------------------------------|
| **Increased Administrative Work** | Managing custom IAM policies can require a lot of extra work. This includes creating, testing, and updating policies regularly to keep up with changing security needs. |
| **Complexity**                  | As the number of custom policies and resources increases, things can get complicated. It might be hard to keep track of everything and manage all the different policies. |
| **Need for Expertise**          | Creating effective custom IAM policies requires knowledge of how IAM works, understanding the specific settings for the cloud platform, and knowing your organization's security needs. This might mean you need to train your team or hire skilled people to handle it. |
| **Risk of Mistakes**            | If custom IAM policies are set up incorrectly, they can create security issues or block access to important resources. Errors can happen during policy creation or updates, which can lead to big problems. |
| **Potential for Over-Restrictions** | Sometimes, custom policies can be too strict, preventing users from accessing the resources they need to do their jobs. This can slow down productivity and create frustration among team members. |

 ***

 ## Create custom IAM policies

### Step1: Navigate to the IAM Service & Go to policies 
![Screenshot from 2024-10-09 18-47-41](https://github.com/user-attachments/assets/ad772223-8b86-4dc4-80e0-c7216dfdd10f)

***
Click on create policy
![Screenshot from 2024-10-09 18-48-43](https://github.com/user-attachments/assets/a892c057-c973-4054-a3ef-e7dbc6197f77)

***
### Step 2: Select a Policy Creation Method & Define Permissions
![Screenshot from 2024-10-09 18-51-13](https://github.com/user-attachments/assets/81a490be-4d35-4203-a4c7-32cff2f54c96)

***
### Step 3: Review the Policy
![Screenshot from 2024-10-09 18-53-01](https://github.com/user-attachments/assets/e3a2809d-3c1d-4114-b339-e03a36bcafd6)

***
### Step 4: Create Successfully
![Screenshot from 2024-10-09 18-55-21](https://github.com/user-attachments/assets/e49fd178-2f1e-4b6a-a760-170c2e30758b)

*** 
## Best Practices for Custom IAM Policies

| Best Practice                    | Explanation                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------------------|
| **Principle of Least Privilege** | Always grant users the minimum permissions they need to perform their tasks. This helps reduce the risk of accidental or malicious actions. |
| **Use Policy Variables**         | Take advantage of policy variables to create dynamic policies. This allows you to customize access based on specific attributes, like user roles or resource tags. |
| **Regularly Review Policies**    | Regularly check and update your IAM policies to ensure they are still relevant and secure. Remove any unnecessary permissions to keep your environment safe. |
| **Test Policies Before Deployment** | Always test new or updated policies in a safe environment before applying them to production. This helps catch any errors that could lead to security issues or access problems. |
| **Document Policies Clearly**    | Keep clear documentation of what each policy does and why it was created. This makes it easier for others to understand and manage the policies in the future. |
| **Use Managed Policies When Possible** | Consider using AWS-managed policies for common use cases. They are maintained by AWS, ensuring that they follow best practices and are regularly updated. |

 
***


 ## Conclusion
Custom IAM policies allow organizations to manage access to AWS resources carefully, helping them meet security standards. They provide better control and security, but they can also be complicated and require more management. However, the advantages of enforcing the principle of least privilege (giving only the necessary permissions) and being able to scale outweigh these challenges. This makes custom IAM policies very important for keeping AWS environments secure. In summary, custom IAM policies are essential for organizations that want detailed access control and strong security in their AWS systems. 


## Contact Information

|     Name         | Email  |
| -----------------| ------------------------------------ |
| Aayush Gaur   | aayush.gaur.snaatak@mygurukulam.co |
***

## References

| Description                                   | References  
| --------------------------------------------  | -------------------------------------------------|
| Link |https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html|
