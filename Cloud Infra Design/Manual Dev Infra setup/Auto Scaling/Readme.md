

# Setup Auto Scaling for Salary API

![Auto Scaling](https://github.com/CodeOps-Hub/Documentation/assets/156056444/96dc6672-d14f-41f4-8f2f-7d6642840df2)

|
| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 19-09-2024         | 0.2        | Brij Singh   | Mutable and Immutable Infrastructure              |


---

## 📑 Table of Contents

1. [Introduction](#Introduction)
2. [Pre-requisites](#Pre-requisites)
3. [Steps to Setup Auto Scaling](#Steps-to-Setup-Auto-Scaling)
4. [Output](#Output)
5. [Conclusion](#Conclusion)
6. [Contact Information](#Contact-Information)
7. [References](#References)

---

## 🌟 Introduction

**Amazon EC2 Auto Scaling** helps manage the right number of EC2 instances to handle your application's workload. You can define the minimum, maximum, and desired instance counts in an **Auto Scaling group**. Auto Scaling will automatically launch or terminate instances based on application demand, ensuring cost efficiency and steady performance.

---

## 🔑 Pre-requisites

- Access to the AWS Management Console or AWS CLI with appropriate permissions.
- Knowledge of your application's [network requirements]
---

## 🛠️ Steps to Setup Auto Scaling

### Step 1: Create an AMI Image of the Salary API Instance

1. Go to the [Amazon EC2 console](https://console.aws.amazon.com/ec2/).
2. Select the **Dev-salary-API** instance, and choose `Actions --> Image and templates --> Create image`.
3. Name your AMI and add a description.
4. Click **Create image**.

   The AMI will appear under the **AMIs** section after creation.
///

---

### Step 2: Create a Launch Template

1. In the EC2 console, go to **Launch Templates** and click **Create launch template**.
2. Give the template a name and description.
3. Select the previously created AMI.
4. Choose the instance type and key pair.
5. Configure network settings as needed.
6. Optionally, add a user data script for custom setup.

   ```bash
   #!/bin/bash
   java -jar Salary-API/target/salary-0.1.0-RELEASE.jar
   ```

7. Click **Create launch template**.

////

---

### Step 3: Create an Auto Scaling Group

1. Open **Auto Scaling Groups** in the EC2 console.
2. Click **Create Auto Scaling group** and name it.
3. Select your launch template.
4. Choose your **VPC** and subnets for availability zones.
5. Optionally, link your Auto Scaling group to a **Load Balancer**.
6. Define the group size, scaling policies, and desired instance count.
7. Optionally, set up notifications and tags.
8. Review and create your Auto Scaling group.

///
---

## 📊 Output

Once the Auto Scaling group is created, EC2 instances will automatically scale based on demand


///

---

## 🎯 Conclusion

Amazon EC2 Auto Scaling ensures that your application is always running the right number of instances. It handles demand fluctuations, optimizes performance, and minimizes costs with simple configuration steps.

---

## 📧 Contact Information

For any queries or further information, feel free to contact:

| 👨‍💻 Name | 📧 Email Address |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |
---

## 🔗 References

| Description                               | Link                                                                                                  |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Documentation Template                    | [Application-Template](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) |
| Cloud Infra Design                        | [Dev Infra Design](https://github.com/CodeOps-Hub/Documentation/blob/main/Application_CI/Design/09-%20Cloud%20Infra%20Design/Cloud-Infra-Design-Dev.md) |
| Create Launch Template                    | [AWS Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-launch-template.html) |
| Create Auto Scaling Group                 | [AWS Docs](https://docs.aws.amazon.com/autoscaling/ec2/userguide/create-asg-launch-template.html) |
