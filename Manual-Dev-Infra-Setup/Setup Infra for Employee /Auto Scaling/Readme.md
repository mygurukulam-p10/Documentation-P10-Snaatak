



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



5. Click **Create image**.
   ![image](https://github.com/user-attachments/assets/42ad3c01-a22a-4eec-bbee-1576c8b8777f)

6.The AMI will appear under the **AMIs** section after creation.
   
![Screenshot from 2024-10-09 11-05-51](https://github.com/user-attachments/assets/8658d92c-c5ec-41c9-8db4-c4cd9e79c7c9)


---

### Step 2: Create a Launch Template

1. In the EC2 console, go to **Launch Templates** and click **Create launch template**.
  ![Screenshot from 2024-10-09 11-12-50](https://github.com/user-attachments/assets/962dd221-6559-40e8-bcad-f11ada8d90c1)




2. Give the template a name and description.
 ![Screenshot from 2024-10-09 11-10-03](https://github.com/user-attachments/assets/c4db740c-e5dd-4a1e-81ed-2f028208d3b2)


3. Select the previously created AMI.
![Screenshot from 2024-10-09 11-10-46](https://github.com/user-attachments/assets/234a8d9b-38cd-45ca-88ba-59fd34988855)


4. Choose the instance type and key pair.
 ![Screenshot from 2024-10-09 11-11-21](https://github.com/user-attachments/assets/d8426aab-92a7-488d-a72b-02f0504739b3)

 

5. Configure network settings as needed.
 ![Screenshot from 2024-10-09 11-12-22](https://github.com/user-attachments/assets/bf3416b4-92d4-47f9-b0bd-10494dc98cc8)

 

11. Click **Create launch template**.
![Screenshot from 2024-10-09 11-12-50](https://github.com/user-attachments/assets/a7a2e52d-e306-40ed-9ebf-31d09077a6ed)


---

### Step 3: Create an Auto Scaling Group


1. Open **Auto Scaling Groups** in the EC2 console.
![Screenshot from 2024-10-09 11-17-09](https://github.com/user-attachments/assets/e167d642-93b8-412e-b842-ccc8d771305c)


2. Click **Create Auto Scaling group** and name it.
![Screenshot from 2024-10-09 11-18-31](https://github.com/user-attachments/assets/aac5c755-eaed-4224-9deb-0343f4c016b1)


3. Select your launch template.
 ![Screenshot from 2024-10-09 11-18-42](https://github.com/user-attachments/assets/33ccda70-6865-4b25-9e7f-c4136a236956)

 
4. Choose your **VPC** and subnets for availability zones.

![Screenshot from 2024-10-09 11-19-18](https://github.com/user-attachments/assets/93db40ef-21f5-43e7-bcfe-b6ca25ceaa7b)

![Screenshot from 2024-10-09 16-55-04](https://github.com/user-attachments/assets/0b0f857c-6e9d-4862-891c-b6029252b895)

5. Optionally, link your Auto Scaling group to a **Load Balancer**.

![Screenshot from 2024-10-09 18-15-02](https://github.com/user-attachments/assets/786bb7bf-25d2-4ba2-adf1-59a72f71bf8d)

6. Define the group size, scaling policies, and desired instance count.
![Screenshot from 2024-10-09 18-15-29](https://github.com/user-attachments/assets/3c453a0a-01f0-402e-84b9-60305f8f59c7)

7. Review and create your Auto Scaling group.


---

## 📊 Output

Once the Auto Scaling group is created, EC2 instances will automatically scale based on demand

![Screenshot from 2024-10-09 18-19-29](https://github.com/user-attachments/assets/1d7901e8-b74e-4f6e-b68d-275ba4c7ba6b)
![Screenshot from 2024-10-09 19-00-53](https://github.com/user-attachments/assets/bbc5e7fb-1d3c-4afd-bce6-bfc6697aa8a5)


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

