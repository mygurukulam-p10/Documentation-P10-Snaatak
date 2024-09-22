# ![jenkins 156x256 (1)](https://github.com/user-attachments/assets/03dbbbb1-945c-4e34-878a-feb7b6c71d80) Jenkins High Availability


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  21-09-24   | Version 1  |    Megha Tyagi      | 21-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [🌟 What is Jenkins?](#-what-is-jenkins)
3. [🛠️ Features of Jenkins](#-features-of-jenkins)
   - [A variety of plugins](#1-a-variety-of-plugins)
   - [Simple installation and configuration](#2-simple-installation-and-configuration)
   - [Open-source](#3-open-source)
   - [Extensibility](#4-extensibility)
   - [Server-based Security](#5-server-based-security)
   - [Easy Distribution](#6-easy-distribution)
4. [📜 Conclusion](#-conclusion)
5. [📚 References](#-references ) 
6. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
The purpose of this document is to provide a comprehensive overview of key features and functionalities of Jenkins. It aims to explain important aspects such as its extensibility, server-based security features, and ease of distribution. By detailing these features, the document seeks to help users understand how Jenkins can be effectively utilized and customized to meet their Continuous Integration and Continuous Delivery (CI/CD) needs. Additionally, it offers insights into the tools and capabilities Jenkins provides to enhance build automation, manage security, and streamline development workflows.

# 🌟 What is High Availibility?
High availability means that an IT system, component, or application can operate at a high level, continuously, without intervention, for a given time period. High-availability infrastructure is configured to deliver quality performance and handle different loads and failures with minimal or zero downtime.

# 💥How to configure Jenkins with High Availability?
Jenkins is the crucial component of DevOps and you may be set up Jenkins in production, but when it comes to the production end, things become more important but if something goes down or an event occurs, such as an increase in load. As a result, it could impact production and cause it to halt. So, you can configure Jenkins’ instantaneous live backup.
Here, will see how to set up Jenkins, how to create pipelines, nodes and make Jenkins available.

### There is two thing:

**Jenkins master-slave setup,**

**Jenkins HA(High Availability)**

## 1. What is Master-slave configuration?
The term “master-slave” describes the high availability of a Jenkins node, such as the master node, which is a single built-in node that can distribute the burden of testing, building, and deploying an application across several slave or agent servers. The Jenkins slave nodes are assigned tasks by the master node, which manages job scheduling, while the slave nodes, also known as agent nodes, are responsible for building, testing, and deploying the application. Jenkins machines’ scalability, availability, and resource efficiency were all improved by the master-salve setup.

![1_AyAzlF4KshptPF58y0qSiA](https://github.com/user-attachments/assets/6bda7be1-f17f-48d1-85eb-d3fef24a8151)

## 2. What is Jenkins HA ?
Here, “high availability” for Jenkins refers to the availability of the Jenkins instance; however, in the unfortunate scenario that your Jenkins server crashes and something goes wrong with the Jenkins instance, another instance will quickly arise and contain all of the data from the primary Jenkins instance. In to this blog, autoscaling groups can be used to achieve Jenkins HA.

<img width="550" alt="Untitled" src="https://github.com/user-attachments/assets/cb231fcd-6a36-42a0-932f-90189bea2c82">

Now, let’s start to set up the master-slave architecture and highly available Jenkins,

### Steps for setting up the Jenkins HA:
**Step-1 :** Create an EC2 instance on requirement bases for Jenkins and create an security group allow the traffic on port 22 for SSH and port 8080 for Jenkins and attach those to the instance.

**Step-2 :** Login to the instance and configure the Jenkins in that instance using following steps:

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

**Step-3 :** After login to the Jenkins instance go to the Manage Jenkins section and then go to the nodes where you can see there is already a pre-built node name as built-in node which is master node.

![Screenshot 2024-09-22 130708](https://github.com/user-attachments/assets/c9c92477-39a6-4978-9f3a-9353adea6430)

**Step-4 :** Now create one slave node,

-> Click on the new node then write a name and select the type as permanent agent and then create a node.

![0_U5GaMlyEaBctXpy9](https://github.com/user-attachments/assets/6e5e7118-2a68-4666-b4e9-37ac4a3a1fa0)

-> Configure the node as the requirement bases.

<img width="550" alt="new" src="https://github.com/user-attachments/assets/972534ee-d372-4b7d-907b-918762f9c821">

-> In the Usage section there are two options. Here, you can configure how Jenkins should use nodes:

Use this node as much as possible: Jenkins will try to utilize this node for as many jobs as possible.

Only build jobs with label expressions matching this node: Jenkins will only use this node if the job specifies the appropriate label(s).

-> Then select the launch method and availability then click “Save” to apply the changes.

<img width="550" alt="data" src="https://github.com/user-attachments/assets/19e4be3e-da6d-4d02-a0d6-ec6351153a17">

<img width="550" alt="data-1" src="https://github.com/user-attachments/assets/caedad02-fd6e-4538-9cf4-7ec5ce00659a">

-> Then, run the below commands to make the node online:

```
curl -sO http://54.225.4.205:8080/jnlpJars/agent.jar
java -jar agent.jar -url http://54.225.4.205:8080/ -secret 1c3ad6f1459b28508907cb559913330a964c3d95bcbf8995822e7c154171ef94 -name slave -workDir "/home/ubuntu/slave"
```
/home/ubuntu/slave — directory which will provided in the slave node configuration

![Screenshot 2024-09-22 152106](https://github.com/user-attachments/assets/ff197d62-e85e-4f56-94f2-35a6f5cdf3b3)

![Screenshot 2024-09-22 152201](https://github.com/user-attachments/assets/b19247ba-5b22-4b76-92bd-2572c427b65f)

**Step-5 :** If you want to run selected jobs on the agent node so for that in the agent node configuration write down the label for the agent node.

<img width="564" alt="next" src="https://github.com/user-attachments/assets/f3c3f358-55db-4d66-a532-ee6393fb703c">

And give the label name in the pipeline code which you want to run on the agent node.

![Screenshot 2024-09-22 152727](https://github.com/user-attachments/assets/09808fad-b40e-4677-a9ff-0682409e5360)

**Step-6 :** After making a slave agent online create an AMI of the Jenkins primary instance.

![Screenshot 2024-09-22 153011](https://github.com/user-attachments/assets/d2fd176a-551f-4c4f-8c99-f445a392eabf)

![Screenshot 2024-09-22 153028](https://github.com/user-attachments/assets/41f42c41-ae89-4309-bfc3-ae926e120656)

**Step-7 :** Then create a Launch template for Auto scaling group using Jenkins primary instance.

![Screenshot 2024-09-22 155404](https://github.com/user-attachments/assets/677a237e-a016-4214-8eec-f2ffcb62b5d6)

![Screenshot 2024-09-22 155713](https://github.com/user-attachments/assets/94b76f87-e45c-4652-b169-0c019fcdacb2)










There is a difference between master-slave setup and HA. So, let’s have a look on that:

So, in this blog there is two thing:

Jenkins master-slave setup,
Jenkins HA(High Availability)

## There are two ways you can have Jenkins in HA mode.

### 1. Jenkins active/passive setup:
Only enterprise Jenkins comes with a supported plugin to have this setup. But most organizations use open-source versions, and this option is out of scope. Also there is an option with HAproxy, however I think its bit of an administrative overhead.



**Jenkins HA setup in autoscaling Group:** Having Jenkins in autoscaling group is workaround to have a higly available Jenkins. It is not a 100% HA solution; however, for any reason if your Jenkins server crasher, another instance will come up within a short period.




## Let's discuss all the features in detail:

## 1. A variety of plugins
Jenkins plugins are extensions that enhance Jenkins' capabilities by integrating CI/CD tools, sources, and destinations, and expanding its functionality. With around 1,500 plugins available, they allow for extensive customization, enabling Jenkins to integrate with other software, add UI components, and improve build and source code management. Plugins can be installed via the Jenkins Web UI or CLI from the Jenkins Plugin repository.
Here are a few important plugins and their use cases:

|🔧 **Plugin Name**     | 📊**Description**                                              | 🌟**Key Features**                                            | 🎯**Use Cases**                                                                 |
|---------------------|--------------------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------------------------|
| **Pipeline**        | Enables continuous delivery pipelines as code.               | Pipeline-as-code, multibranch pipelines, visual pipeline UI  | Automating the build, test, and deploy process for complex projects.           |
| **Git**             | Integrates Git version control with Jenkins.                 | Clone repositories, track branches, trigger builds on changes| Automating builds and deployments based on changes in Git repositories.        |
| **Blue Ocean**      | Provides a modern UI for Jenkins pipelines.                  | Simplified, visual pipeline view, improved user experience   | Managing and viewing Jenkins pipelines in an easy-to-use interface.            |
| **JUnit**           | Publishes test results generated by JUnit or other test suites| Visualize test results, historical data, and trends          | Tracking unit test results and generating reports for test execution outcomes. |
| **Docker**          | Provides Docker build and run capabilities in Jenkins.       | Build Docker images, manage containers, use Docker agents    | Automating Docker workflows, building images, and managing containers in pipelines. |
| **Credentials**     | Manages and stores credentials securely within Jenkins.      | Centralized credential management, easy access for jobs      | Handling sensitive information like SSH keys, API tokens, and passwords securely.|


## 2. Simple installation and configuration
|  ⏳**Aspect**                                            |📄 **Description**                                                                                         |
|---------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| **Cross-platform compatibility**                        | Jenkins is a self-contained Java software that runs on all major operating systems (Windows, Unix, Mac OS). |
| **Easy setup and configuration**                        | It provides a web interface with built-in error checks and help features for easy setup and configuration. |
| **Installation options**                                | Available as a standard installation package or as a `.war` file.                                         |
| **Web-based configuration**                             | Can be quickly configured through the web interface after installation.                                   |
| **Extensive support and documentation**                 | Jenkins has a large knowledge base, detailed documentation, and a thriving community for support.          |
| **Learning materials**                                  | Provides learning resources for easier installation, management, and troubleshooting.                     |
| **Production pipeline complexity**                      | Production pipelines can be challenging and require Jenkinsfiles using declarative or scripted coding.     |


## 3. Open-source

|⏳ **Aspect**                     | 📄**Details**                                                                                               |
|---------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Open-source Availability**    | Jenkins is free and open-source, meaning it has no licensing costs, and its source code is available for modification, making it highly flexible. The large community contributes to continuous improvements, bug fixes, and plugin development. |
| **Customization and Flexibility** | Jenkins supports a wide range of plugins and integrations, allowing users to tailor it to their specific CI/CD needs. |
| **Community and Support**       | Being open-source, Jenkins has a large, active community that provides extensive resources, tutorials, and forums for troubleshooting. |
| **Cost-effective**              | Jenkins has no associated licensing fees, making it a budget-friendly option for both small and large teams. |
| **Security**                    | Regular security patches are released by the community, and it provides built-in authentication and authorization capabilities. |
| **Frequent Updates**            | The open-source nature ensures continuous updates and new features from community contributions and Jenkins maintainers. |


## 4. Extensibility

| ⏳**Aspect**                    | 📄**Details**                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------|
| **Extensibility**              | Jenkins can be extended with over 1,500 plugins, allowing it to integrate with a wide range of tools, technologies, and services. |
| **Custom Pipeline Creation**   | Users can create custom pipelines using scripted or declarative pipeline syntax to suit various workflows and automation tasks. |
| **Integration with Other Tools** | Jenkins seamlessly integrates with popular DevOps tools like Docker, Kubernetes, AWS, and more, enhancing CI/CD workflows. |
| **Custom UI Enhancements**     | Jenkins allows UI enhancements and modifications through plugins, improving the user experience and interface functionality. |
| **Community-Contributed Plugins** | Many plugins are contributed by the Jenkins community, providing diverse functionality and ensuring that Jenkins evolves with new technologies. |


## 5. Server-based Security 

|⏳ **Aspect**                     |📄 **Details**                                                                                               |
|---------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Role-based Access Control**   | Jenkins allows defining roles and permissions for different users or groups, restricting access to sensitive parts of the system. |
| **Authentication**              | Supports multiple authentication methods like LDAP, Active Directory, OAuth, and SSO, ensuring secure user logins. |
| **Authorization**               | Jenkins enables fine-grained authorization strategies, allowing admins to control user access based on roles, jobs, or even specific pipelines. |
| **SSL/TLS Support**             | Jenkins supports SSL/TLS encryption to secure communication between the server and clients, protecting data integrity and confidentiality. |
| **Audit Logs**                  | Provides detailed logging of user actions, job executions, and system events, helping to monitor and detect unauthorized activities. |
| **Credential Management**       | Jenkins has built-in secure credential management, storing sensitive information like SSH keys, API tokens, and passwords in an encrypted format. |

## 6. Easy Distribution 

| ⏳**Aspect**                     | 📄**Details**                                                                                               |
|--------------------------------|-----------------------------------------------------------------------------------------------------------|
| **Master-Slave Architecture**  | Jenkins supports a master-slave architecture where the master node handles scheduling and monitoring, while slave nodes run the build tasks. This helps distribute the workload and improves performance. |
| **Distributed Builds**         | Enables running builds on multiple machines or nodes, which can be located on different servers or cloud environments, allowing for efficient resource utilization. |
| **Cloud Integration**          | Jenkins integrates with various cloud services (e.g., AWS, Azure, Google Cloud) for dynamic scaling of build agents, automating distribution, and managing build infrastructure. |
| **Docker Integration**         | Jenkins can leverage Docker to create isolated build environments, which can be easily distributed across different servers or containers, enhancing consistency and scalability. |
| **Multi-Node Setup**           | Allows setting up Jenkins across multiple nodes to distribute build and test jobs, reducing the load on a single server and improving build times. |
| **Job Distribution**           | Jenkins can distribute build jobs across different nodes based on labels or capabilities, optimizing job execution and balancing the load. |


## 📜 Conclusion
In summary, Jenkins offers a robust and versatile platform for Continuous Integration and Continuous Delivery (CI/CD) with its extensive range of features and capabilities. Its open-source nature, combined with its extensibility through plugins, makes Jenkins a powerful tool for automating and optimizing development workflows. The server-based security features ensure that Jenkins can be securely integrated into various environments, while its easy distribution capabilities support scalable and efficient build management. Understanding these aspects allows users to leverage Jenkins effectively, customize it to their needs, and enhance their overall CI/CD processes. This document serves as a foundational resource to guide users in exploring and utilizing Jenkins to its fullest potential.
 
## 📚 References 
|links | Description |
|-------|------------|
|https://www.spiceworks.com/tech/devops/articles/what-is-jenkins/#_005|**Spiceworks** |
|https://www.geeksforgeeks.org/what-is-jenkins/| **GreekforGreek**|
|https://www.jenkins.io/|**Jenkins**|

## 📧 Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Megha Tyagi**|megha.tyagi.snaatak@mygurukulam.co|

