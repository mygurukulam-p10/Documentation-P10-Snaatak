


# Setup Auto Scaling for Attendance API



| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 08-10-2024  | Version 1.0  | Megha Tyagi     | 08-10-2024     |


---

## 📑 Table of Contents

1. [🌟 Introduction](#-introduction)
2. [🔑 Pre-requisites](#-pre-requisites)
3. [🛠️ Steps to Setup Auto Scaling](#-steps-to-setup-auto-scaling)
4. [📊 Output](#-output)
5. [🎯 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [🔗 References](#-references)

---

## 🌟 Introduction

**Amazon EC2 Auto Scaling** helps manage the right number of EC2 instances to handle your application's workload. You can define the minimum, maximum, and desired instance counts in an **Auto Scaling group**. Auto Scaling will automatically launch or terminate instances based on application demand, ensuring cost efficiency and steady performance.

---

## 🔑 Pre-requisites

- Access to the AWS Management Console or AWS CLI with appropriate permissions.
- Knowledge of your application's [network requirements]
---

## 🛠️ Steps to Setup Auto Scaling

### Step 1: Create an AMI Image of the Attendance API Instance

1. Go to the [Amazon EC2 console](https://console.aws.amazon.com/ec2/).
   <img width="949" alt="image" src="https://github.com/user-attachments/assets/437d6e87-958d-4c4f-bf78-2290063baf0c">


2. Select the **OTMS-Dev-Attendance-Ec2** instance, and choose `Actions --> Image and templates --> Create image`.

  ![Screenshot 2024-10-09 002744](https://github.com/user-attachments/assets/27c69bd4-64f3-4cc9-8f53-210b67debb8d)

3. Name your AMI and add a description.
 
![Screenshot 2024-10-09 003916](https://github.com/user-attachments/assets/34a62e84-9195-478d-887b-06030bdbe842)


4. Click **Create image**.

![image](https://github.com/user-attachments/assets/42ad3c01-a22a-4eec-bbee-1576c8b8777f)


5.The AMI will appear under the **AMIs** section after creation.
   
<img width="959" alt="image" src="https://github.com/user-attachments/assets/b4e76ea9-65eb-4440-88cf-4509c3d7d0e6">



---

### Step 2: Create a Launch Template

1. In the EC2 console, go to **Launch Templates** and click **Create launch template**.
   
![Screenshot 2024-10-09 004033](https://github.com/user-attachments/assets/14692457-1dd7-4dda-b044-3d8071131c8a)


2. Give the template a name and description.
 
<img width="947" alt="image" src="https://github.com/user-attachments/assets/1fad894a-00bd-4805-94e9-19c4f88f5ffa">


3. Select the previously created AMI.

 !![Screenshot 2024-10-09 004433](https://github.com/user-attachments/assets/2e2ea706-be17-4e56-8e5d-cd81be109c3f)


4. Choose the instance type and key pair.
 
 ![Screenshot 2024-10-09 004310](https://github.com/user-attachments/assets/bd53ce9f-74ee-4633-8078-af4ea7681bc9)


5. Configure network settings as needed.
 ![Screenshot 2024-10-09 004409](https://github.com/user-attachments/assets/d1d3defe-323d-4ac9-a864-a22b6b59c28b)



6. Click **Create launch template**.

![Screenshot 2024-10-09 004433](https://github.com/user-attachments/assets/4abb743f-83e5-44a0-9904-8f4ee9051d0e)

---

### Step 3: Create an Auto Scaling Group

1. Open **Auto Scaling Groups** in the EC2 console.

![Screenshot 2024-10-09 004519](https://github.com/user-attachments/assets/ccd568b2-468c-4f0e-b14e-81e41c1b3750)


2. Click **Create Auto Scaling group** and name it.

3. Select your launch template.
 
<img width="947" alt="image" src="https://github.com/user-attachments/assets/69bbb2ba-1fd2-4edb-a05a-2f60447a29b8">


4. Choose your **VPC** and subnets for availability zones.

![Screenshot 2024-10-09 004645](https://github.com/user-attachments/assets/5c1159c3-7363-4c29-92b3-3fea04cca53f)


5. Optionally, link your Auto Scaling group to a **Load Balancer**.

6. Define the group size, scaling policies, and desired instance count.
![Screenshot 2024-10-09 084623](https://github.com/user-attachments/assets/61053530-e59c-4049-be74-8a562630698e)



7. Optionally, set up notifications and tags.
![Screenshot 2024-10-09 084658](https://github.com/user-attachments/assets/84a227e9-0bdd-450d-87f0-f8fbd7460edd)


8. Review and create your Auto Scaling group.

![Screenshot 2024-10-09 084731](https://github.com/user-attachments/assets/0fa449c3-712f-4cd7-94e8-b689af854938)
![Screenshot 2024-10-09 084744](https://github.com/user-attachments/assets/e6f9ad7f-d922-4ba5-a705-70241f0f1d04)



---

## 📊 Output

Once the Auto Scaling group is created, EC2 instances will automatically scale based on demand

![Screenshot 2024-10-09 084834](https://github.com/user-attachments/assets/2aafb566-7099-49b4-bcca-358125bca00f)



---

## 🎯 Conclusion

Amazon EC2 Auto Scaling ensures that your application is always running the right number of instances. It handles demand fluctuations, optimizes performance, and minimizes costs with simple configuration steps.

---

##  📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |

---

## 🔗 References

| **Description**                               | **Link**    |
| ----------------------------------------- | --------------------------------------------------------------------------------|
| Create Launch Template                    | [AWS Docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/create-launch-template.html) |
| Create Auto Scaling Group                 | [AWS Docs](https://k21academy.com/amazon-web-services/aws-solutions-architect/aws-auto-scaling/) |
