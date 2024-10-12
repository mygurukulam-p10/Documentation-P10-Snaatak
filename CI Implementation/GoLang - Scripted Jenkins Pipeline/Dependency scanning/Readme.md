# Dependency Scanning - OWASP Dependency-Check Jenkins Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|----------------|----------------|---------------|--------------------|-------------------|
| Amit Nagar     | 05-10-2024     | Version 1     | Amit Nagar         | 05-10-2024        |

---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration Dependency Scanning](#-steps-to-configuration-dependency-scanning)
5. [Jenkinsfile](#Jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

## ⭐ Introduction 
This document provides an overview of implementing dependency scanning in a project using OWASP Dependency-Check in a Jenkins scripted pipeline.


---
## ⚙️ Prerequisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**        | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Snyk CLI**       | Snyk CLI must be installed on the Jenkins server.                           |
| **✔️ Git**            | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**| Add your GitHub credentials (e.g., git-token) in Jenkins for repository access. |
| **✔️ Snyk API Token** | Add your Snyk API token in Jenkins to authenticate Snyk scans.              |

## 🔍 System Requirements

## Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                          |
| **Memory (RAM)**     | Minimum 4 GB                                   |
| **Storage**          | Minimum 20 GB|
| **Operating System** | Ubuntu 22.04       |


# Snyk Plugin Installation and Configuration for Jenkins

## Steps to Install and Configure the Snyk Plugin

### 1. Install the Snyk Plugin:
- Navigate to **Jenkins Dashboard > Manage Jenkins > Manage Plugins**.
- Under the **Available** tab, search for **Snyk Security**.
- Install the **Snyk Security** plugin.
![Screenshot from 2024-10-12 01-58-44](https://github.com/user-attachments/assets/76ff563d-ec51-45c7-bf59-b87bb2534d48)


### 2. Configure the Snyk Plugin:
- After installing the plugin, go to **Jenkins Dashboard > Manage Jenkins > Configure System**.
- Scroll down to the **Snyk** section.
- Enter your **Snyk API Token** (you can generate it from your Snyk account under **Account Settings**).
- Click **Save** to apply the changes.

- ![Screenshot from 2024-10-12 02-36-07](https://github.com/user-attachments/assets/95268ff4-1a89-4773-b3a7-11104847f05e)


### 3. Configure Snyk Tool in Jenkins:
- Navigate to **Jenkins Dashboard > Manage Jenkins > Global Tool Configuration**.
- Under the **Snyk** section, click **Add Snyk**.
- Provide a name for the tool (e.g., `Snyk`).
- Specify the installation method (manual or automatic).
  - For **automatic installation**, Jenkins will download Snyk automatically.
  ![Screenshot from 2024-10-12 02-08-17](https://github.com/user-attachments/assets/2287c7c1-3d5b-44cf-a3ad-bec3f77d39a1)



# Steps to Configuration Dependency Scanning
### 1. 🚀 Open your Jenkins Dashboard.

### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `Dependency Scanning`).

![Screenshot from 2024-10-11 20-41-10](https://github.com/user-attachments/assets/664e5b1c-81ea-47dc-a7f3-44880f853b40)


### 3. 🚀 Provide a description for the pipeline in detail about what it will perform.
![Screenshot from 2024-10-11 20-41-28](https://github.com/user-attachments/assets/d35d2e13-a140-46e2-bb24-ae3a2268def2)
### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for dependency scanning in the pipeline configuration...>Click on Save to store the configuration.
![Screenshot from 2024-10-12 11-53-58](https://github.com/user-attachments/assets/0602c080-537d-4675-81c7-5cc9c24f4f86)

![Screenshot from 2024-10-12 11-54-03](https://github.com/user-attachments/assets/8c724263-7ad3-4d78-ae9b-9f6461d74a64)

### 5. 🚀 Then Click on build to run the pipeline to perform dependency scanning.
![Screenshot from 2024-10-12 10-38-20](https://github.com/user-attachments/assets/8955da9b-ed8d-4a08-a7a8-6f1f487cecc3)


### 6. 🚀 Now we are able to see build complete.
![Screenshot from 2024-10-12 11-32-05](https://github.com/user-attachments/assets/bd6d95a5-ea96-497e-9da4-7b6cbfd12283)

### 7. 🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-12 11-43-53](https://github.com/user-attachments/assets/b8f4fc28-b689-4417-8abb-12bfddf9c2b5)


![Screenshot from 2024-10-12 11-44-02](https://github.com/user-attachments/assets/cd011db4-0f44-4d9f-a0c3-a509a85d982f)


### 8. 🚀 Review the results of the dependency scanning in the console output.
![Screenshot from 2024-10-12 11-32-17](https://github.com/user-attachments/assets/a654dad5-91c5-41f2-9586-d26f8fee96f6)

# Jenkinsfile
```

node {
    // Set up Go and Snyk tool paths
    def goTool = tool name: 'golang', type: 'go'
    env.PATH = "${goTool}/bin:${env.PATH}"

    stage('Clone Repository') {
        // Clone the specified repository from GitHub
        git branch: 'main', url: 'git@github.com:mygurukulam-p10/employee-api.git', credentialsId: "amit_cred"
    }

    stage('Run Snyk Test') {
        // Run Snyk test command to generate the report
        script {
            snykSecurity(
          snykInstallation: 'snyk',
          snykTokenId: 'snyk_token',
    
        )
        }
    }
}
```


## 🏁 Conclusion
The dependency scanning stage successfully analyzes the project's dependencies, identifying any known vulnerabilities and providing a report to ensure the application is secure.

## 📞 Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## 📚 References

| Topic                   | Reference Link                                           |
|-------------------------|---------------------------------------------------------|
| Snyk Documentation       | [Snyk Documentation](https://docs.snyk.io/)             |
| Snyk CLI Usage           | [Snyk CLI Documentation](https://docs.snyk.io/snyk-cli) |
| Jenkins Pipeline         | [Jenkins Pipeline](https://www.jenkins.io/doc/book/pipeline/) |
