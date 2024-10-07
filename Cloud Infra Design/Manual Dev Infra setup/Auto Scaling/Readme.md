

# Setup Auto Scaling for Salary API



|
| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 03-10-2024         | 0.1        | Brij Singh   | Auto Scaling              |


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
   ![image](https://github.com/user-attachments/assets/560e9864-7f3f-45bc-937a-247e6f3ac0ae)

2. Select the **OTMS-Dev-ScyllaDB-Salary-Ec2** instance, and choose `Actions --> Image and templates --> Create image`.
   ![image](https://github.com/user-attachments/assets/be10353d-892c-4158-b23e-bc693443b1fa)

3. Name your AMI and add a description.
   ![image](https://github.com/user-attachments/assets/06c2a063-57c7-4692-8413-5d15299eb595)

4. Click **Create image**.
   ![image](https://github.com/user-attachments/assets/42ad3c01-a22a-4eec-bbee-1576c8b8777f)


   5.The AMI will appear under the **AMIs** section after creation.
![image](https://github.com/user-attachments/assets/7a6baf3c-0bef-4493-8da9-922157c4a6ad)


---

### Step 2: Create a Launch Template

1. In the EC2 console, go to **Launch Templates** and click **Create launch template**.
2. ![image](https://github.com/user-attachments/assets/8f6569e6-9c63-439c-a11f-c8ce6bcbe6e7)
![image](https://github.com/user-attachments/assets/40b114ac-13a8-461e-a4a8-e6d3b108408c)

3. Give the template a name and description.
 ![image](https://github.com/user-attachments/assets/0a37d4b1-b6bc-40ed-bd33-7d3b61984935)

4. Select the previously created AMI.
 ![image](https://github.com/user-attachments/assets/3b7a82d8-f020-4e8b-b065-4496c57d7203)

4. Choose the instance type and key pair.
 ![image](https://github.com/user-attachments/assets/778fc49b-3daf-48a2-b42a-0561126647fa)

5. Configure network settings as needed.
 ![image](https://github.com/user-attachments/assets/eae1a248-20a5-411a-b6e3-1642ce7cf1b0)

6 Optionally, add a user data script for custom setup.

   ```bash
   #!/bin/bash
   java -jar Salary-API/target/salary-0.1.0-RELEASE.jar
   ```

11. Click **Create launch template**.

![image](https://github.com/user-attachments/assets/42530798-aa22-417f-b135-48acc1a6960d)


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
| Documentation Template                    | [Application-Template](
| Cloud Infra Design                        | [Dev Infra Design]
| Create Launch Template                    | [AWS Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-launch-template.html) |
| Create Auto Scaling Group                 | [AWS Docs](https://docs.aws.amazon.com/autoscaling/ec2/userguide/create-asg-launch-template.html) |
