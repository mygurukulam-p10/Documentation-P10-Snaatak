# ![jenkins 156x256 (1)](https://github.com/user-attachments/assets/03dbbbb1-945c-4e34-878a-feb7b6c71d80) Jenkins High Availability


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  21-09-24   | Version 1  |    Megha Tyagi      | 22-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [🌟 What is High Availability?](#-what-is-high-availability)
3. [🛠️ How to configure Jenkins with High Availability?](#-how-to-configure-jenkins-with-high-availability)
   - [What is Master-slave configuration?](#1-what-is-master-slave-configuration)
   - [What is Jenkins HA?](#2-what-is-jenkins-ha)
4. [Steps for setting up the Jenkins HA](#steps-for-setting-up-the-jenkins-ha)
5.  [📜 Conclusion](#-conclusion)
6. [📚 References](#-references ) 
7. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
The purpose of this document is to provide a comprehensive guide on configuring Jenkins for high availability (HA) in a production environment. It outlines the importance of ensuring continuous access to Jenkins, even in the event of a primary instance failure. The document details the steps for setting up a master-slave architecture and implementing HA using auto-scaling groups in AWS. Additionally, it demonstrates how to verify the accessibility of Jenkins through a secondary instance. Overall, the guide aims to equip users with the knowledge needed to maintain uninterrupted Jenkins operations.

# 🌟 What is High Availability?
High availability means that an IT system, component, or application can operate at a high level, continuously, without intervention, for a given time period. High-availability infrastructure is configured to deliver quality performance and handle different loads and failures with minimal or zero downtime.

# 💥How to configure Jenkins with High Availability?
Jenkins is the crucial component of DevOps and you may be set up Jenkins in production, but when it comes to the production end, things become more important but if something goes down or an event occurs, such as an increase in load. As a result, it could impact production and cause it to halt. So, you can configure Jenkins’ instantaneous live backup.
Here, will see how to set up Jenkins, how to create pipelines, nodes and make Jenkins available.

## There is two thing:

### Jenkins master-slave setup

### Jenkins HA(High Availability)

## 1. What is Master-slave configuration?
The term “master-slave” describes the high availability of a Jenkins node, such as the master node, which is a single built-in node that can distribute the burden of testing, building, and deploying an application across several slave or agent servers. The Jenkins slave nodes are assigned tasks by the master node, which manages job scheduling, while the slave nodes, also known as agent nodes, are responsible for building, testing, and deploying the application. Jenkins machines’ scalability, availability, and resource efficiency were all improved by the master-salve setup.

![1_AyAzlF4KshptPF58y0qSiA](https://github.com/user-attachments/assets/6bda7be1-f17f-48d1-85eb-d3fef24a8151)

## 2. What is Jenkins HA?
Here, “high availability” for Jenkins refers to the availability of the Jenkins instance; however, in the unfortunate scenario that your Jenkins server crashes and something goes wrong with the Jenkins instance, another instance will quickly arise and contain all of the data from the primary Jenkins instance. In to this blog, autoscaling groups can be used to achieve Jenkins HA.

<img width="550" alt="Untitled" src="https://github.com/user-attachments/assets/cb231fcd-6a36-42a0-932f-90189bea2c82">

Now, let’s start to set up the master-slave architecture and highly available Jenkins,

## Steps for setting up the Jenkins HA
### ⚡Step-1 : 
Create an EC2 instance on requirement bases for Jenkins and create an security group allow the traffic on port 22 for SSH and port 8080 for Jenkins and attach those to the instance.

### ⚡Step-2 : 
Login to the instance and configure the Jenkins in that instance using following steps:

**1. Install Java:** Installing Java on the Ubuntu instance is the first step, as Jenkins needs it to function.

```
sudo apt-get update
sudo apt-get install openjdk-11-jdk
```
**2. Add Jenkins repository:** The next set of instructions to run is to add the Jenkins repository to the instance.

```
sudo curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee   /usr/share/keyrings/jenkins-keyring.asc > /dev/null
sudo echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]   https://pkg.jenkins.io/debian-stable binary/ | sudo tee   /etc/apt/sources.list.d/jenkins.list > /dev/null
```

**3. Install Jenkins:** Now you can install Jenkins by running the following command:

```
sudo apt-get update
sudo apt-get install jenkins
```
**4. Start Jenkins:** Use the following command to launch and enable the Jenkins service after it has been installed.

```
sudo systemctl start jenkins
sudo systemctl status jenkins
```
**5. Configure Jenkins:**
By using your EC2 instance’s public IP address and the default port 8080 (http://ip_address:8080), you may access the Jenkins web interface.
After completing the Jenkins setup wizard by following the on-screen directions, you’ll be asked to input the initial admin password, which is located in the file /var/lib/jenkins/secrets/initialAdminPassword.

### ⚡Step-3 : 
After login to the Jenkins instance go to the Manage Jenkins section and then go to the nodes where you can see there is already a pre-built node name as built-in node which is master node.

![Screenshot 2024-09-22 130708](https://github.com/user-attachments/assets/c9c92477-39a6-4978-9f3a-9353adea6430)

### ⚡Step-4 : Now create one slave node,

-> Click on the new node then write a name and select the type as permanent agent and then create a node.

![0_U5GaMlyEaBctXpy9](https://github.com/user-attachments/assets/6e5e7118-2a68-4666-b4e9-37ac4a3a1fa0)

-> Configure the node as the requirement bases.

<img width="550" alt="new" src="https://github.com/user-attachments/assets/972534ee-d372-4b7d-907b-918762f9c821">

-  **In the Usage section there are two options. Here, you can configure how Jenkins should use nodes:**

**Use this node as much as possible:** Jenkins will try to utilize this node for as many jobs as possible.

**Only build jobs with label expressions matching this node:** Jenkins will only use this node if the job specifies the appropriate label(s).

- **Then select the launch method and availability then click “Save” to apply the changes.**

<img width="550" alt="data" src="https://github.com/user-attachments/assets/19e4be3e-da6d-4d02-a0d6-ec6351153a17">

<img width="550" alt="data-1" src="https://github.com/user-attachments/assets/caedad02-fd6e-4538-9cf4-7ec5ce00659a">

* **Then, run the below commands to make the node online:**

```
curl -sO http://54.225.4.205:8080/jnlpJars/agent.jar
java -jar agent.jar -url http://54.225.4.205:8080/ -secret 1c3ad6f1459b28508907cb559913330a964c3d95bcbf8995822e7c154171ef94 -name slave -workDir "/home/ubuntu/slave"
```
**/home/ubuntu/slave — directory which will provided in the slave node configuration**

![Screenshot 2024-09-22 152106](https://github.com/user-attachments/assets/ff197d62-e85e-4f56-94f2-35a6f5cdf3b3)

![Screenshot 2024-09-22 152201](https://github.com/user-attachments/assets/b19247ba-5b22-4b76-92bd-2572c427b65f)

### ⚡Step-5 : 
**If you want to run selected jobs on the agent node so for that in the agent node configuration write down the label for the agent node.**

<img width="564" alt="next" src="https://github.com/user-attachments/assets/f3c3f358-55db-4d66-a532-ee6393fb703c">

And give the label name in the pipeline code which you want to run on the agent node.

![Screenshot 2024-09-22 152727](https://github.com/user-attachments/assets/09808fad-b40e-4677-a9ff-0682409e5360)

### ⚡Step-6 : 
After making a slave agent online create an AMI of the Jenkins primary instance.

![Screenshot 2024-09-22 153011](https://github.com/user-attachments/assets/d2fd176a-551f-4c4f-8c99-f445a392eabf)

![Screenshot 2024-09-22 153028](https://github.com/user-attachments/assets/41f42c41-ae89-4309-bfc3-ae926e120656)

### ⚡Step-7 : 
Then create a Launch template for Auto scaling group using Jenkins primary instance.

![Screenshot 2024-09-22 155404](https://github.com/user-attachments/assets/f5bdfc9b-6708-414c-8c6e-8a68edd70df5)

### ⚡Step-8 : 
Then, create an Auto scaling group using a launch template on requirement bases, select the desired, maximum and minimum capacity of the instance, create an application load balancer and the target groups and attach those from the ASG.

-**Auto Scaling Group:**

![Screenshot 2024-09-22 160426](https://github.com/user-attachments/assets/754c8747-b047-4953-9250-5d0a1c63a8d6)


- **Target group:**
Check the health status of the Jenkins instance in the target group; both instances should be healthy.

![Screenshot 2024-09-22 155822](https://github.com/user-attachments/assets/14655f4d-4ed3-4ce2-a66c-66d80d2ed470)


- **Load balancer:**
![Screenshot 2024-09-22 160028](https://github.com/user-attachments/assets/ab3c4803-6e88-4a07-b7d6-c8d9c309374c)


## ⚡Step-9 : 
Then, stop the primary instance and see if the load would be transferred to the secondary.

### Primary Jenkins instance:

<img width="439" alt="image" src="https://github.com/user-attachments/assets/8cabb1dc-c1d3-43e6-941e-dc82ee884bde">


Here, The primary instance will be stopped to verify if Jenkins remains accessible via the secondary instance.
<img width="953" alt="image" src="https://github.com/user-attachments/assets/1a877814-0f30-4c55-a1ad-a642ac3cfc81">

### Secondary Jenkins Instance:

<img width="328" alt="image" src="https://github.com/user-attachments/assets/6862df95-861e-4708-831c-847200c1fa0f">


### As demonstrated, we are able to access Jenkins using the secondary instance, which showcases how Jenkins can be made highly available.

## 📜 Conclusion
In conclusion, this document serves as a detailed guide for configuring Jenkins to achieve high availability in a production environment. By implementing a master-slave architecture and utilizing auto-scaling groups in AWS, organizations can ensure continuous access to Jenkins, minimizing downtime during incidents or increased load. The outlined steps for setup, configuration, and verification provide a clear pathway for users to enhance their Jenkins infrastructure. Ultimately, adopting these practices not only improves operational resilience but also supports the overall efficiency of the DevOps pipeline, allowing teams to deliver software reliably and swiftly.
 
## 📚 References 
|links | Description |
|-------|------------|
|https://www.opcito.com/blogs/how-to-configure-jenkins-with-high-availability|**Opcito** |
|https://cscontents.com/jenkins-high-availability/#google_vignette| **CSContents**|
|https://aws.amazon.com/blogs/devops/jenkins-high-availability-and-disaster-recovery-on-aws/|**AWS**|

## 📧 Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Megha Tyagi**|megha.tyagi.snaatak@mygurukulam.co|

