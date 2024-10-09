



<img width="470" alt="1684234129196" src="https://github.com/user-attachments/assets/da7044c3-99d8-4790-8577-10d4e7fc5683">



# Setup Auto Scaling for Employee API


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 09-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |

---
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
   !

2. Select the **OTMS-Dev-Ec2-Employee** instance, and choose `Actions --> Image and templates --> Create image`.
![Screenshot from 2024-10-09 10-56-54](https://github.com/user-attachments/assets/4220d502-bcef-42a9-a0f7-f0b07c1cc431)

   
4. Name your AMI and add a description.
 ![Screenshot from 2024-10-09 10-58-14](https://github.com/user-attachments/assets/3c11344a-2d41-4b36-bc27-89408776bfa5)



6. Click **Create image**.

 5.The AMI will appear under the **AMIs** section after creation.
   
![Screenshot from 2024-10-09 11-05-51](https://github.com/user-attachments/assets/8658d92c-c5ec-41c9-8db4-c4cd9e79c7c9)


---

### Step 2: Create a Launch Template

1. In the EC2 console, go to **Launch Templates** and click **Create launch template**.
   ![Uploading Screenshot from 2024-10-09 11-06-25.png…]()



2. Give the template a name and description.
 

3. Select the previously created AMI.


4. Choose the instance type and key pair.
 
 

5. Configure network settings as needed.
 
 

6 Optionally, add a user data script for custom setup.

   ```bash
   #!/bin/bash
   java -jar Salary-API/target/salary-0.1.0-RELEASE.jar
   ```

11. Click **Create launch template**.


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


---

## 📊 Output

Once the Auto Scaling group is created, EC2 instances will automatically scale based on demand



---

## 🎯 Conclusion

Amazon EC2 Auto Scaling ensures that your application is always running the right number of instances. It handles demand fluctuations, optimizes performance, and minimizes costs with simple configuration steps.

---
## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |


## 🔗 References

| Description                               | Link                                                                                                  |
| ----------------------------------------- | --------------------------------------------------------------------------------
| Create Launch Template                    | [AWS Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-launch-template.html) |
| Create Auto Scaling Group                 | [AWS Docs](https://k21academy.com/amazon-web-services/aws-solutions-architect/aws-auto-scaling/) |

![2021-04-26-17_03_00-Photos](https://github.com/user-attachments/assets/69dc8349-aa1f-453e-96b1-925fef30915d)
