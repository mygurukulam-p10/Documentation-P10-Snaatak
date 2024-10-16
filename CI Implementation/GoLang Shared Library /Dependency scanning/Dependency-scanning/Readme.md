# Dependency Scanning - Jenkins  Shared Pipeline

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on |
|----------------|----------------|---------------|--------------------|-------------------|
| Amit Nagar     | 16-10-2024     | Version 1     | Amit Nagar         | 16-10-2024        |

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
This document provides an overview of implementing dependency scanning in a project using synk in a Jenkins shared pipeline.


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

## Step 1.1: Configure the Shared Library in Jenkins

To configure the shared library in Jenkins globally, follow these steps:

1. Go to the **Jenkins Dashboard**.
2. Click on **Manage Jenkins** → **Configure System**.
3. Scroll down to **Global Pipeline Libraries** and click **Add**.
4. Fill out the details:
   - **Name**: Give your shared library a name (e.g., `shared-library`).
   - **Default Version**: (Optional) Enter the branch, tag, or commit hash (e.g., `main`).
   - **Retrieval Method**: Choose `Modern SCM` and select **Git**.
   - **Repository URL**: Provide the URL to the shared library repository.
   - **Credentials**: If your repository requires authentication, select or add the necessary credentials.
   
 ![Screenshot from 2024-10-16 02-47-49](https://github.com/user-attachments/assets/ae329def-ca32-4a85-bfb0-66bc24e38d54)


5. Click **Save** to apply the configuration.


### 2. 🚀 Click on **New Item**.** ---> **Enter a name for your job (e.g., `shared Dependency Scanning`).
![Screenshot from 2024-10-16 01-53-54](https://github.com/user-attachments/assets/4e8fee46-b748-47da-aa5c-41547db097cb)



### 3. 🚀 Provide a description for the pipeline in detail about what it will perform.
![Screenshot from 2024-10-16 02-43-22](https://github.com/user-attachments/assets/1c7a51a3-f490-4cb1-907b-e5446c1e9007)

### 4. 🚀 Choose Pipeline as the job type-->Add your pipeline script for dependency scanning in the pipeline configuration...>Click on Save to store the configuration.
![Screenshot from 2024-10-12 11-53-58](https://github.com/user-attachments/assets/0602c080-537d-4675-81c7-5cc9c24f4f86)

![Screenshot from 2024-10-16 02-50-57](https://github.com/user-attachments/assets/d7b9ecd4-4917-4a96-9b2e-88cb0e93a2fa)

### 5. 🚀 Then Click on build to run the pipeline to perform dependency scanning.
![Screenshot from 2024-10-12 10-38-20](https://github.com/user-attachments/assets/8955da9b-ed8d-4a08-a7a8-6f1f487cecc3)


### 6. 🚀 Now we are able to see build complete.
![Screenshot from 2024-10-16 02-42-01](https://github.com/user-attachments/assets/8928530e-3184-4a7d-a1e9-19b83fe2bbb6)



### 7. 🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-16 02-41-26](https://github.com/user-attachments/assets/866daa86-777f-468e-bfcb-d447013658bc)
![Screenshot from 2024-10-16 02-41-32](https://github.com/user-attachments/assets/099c5b81-2df4-47f1-a838-b91ffcea3436)


### 8. 🚀 Review the results of the dependency scanning in the console output.
![Screenshot from 2024-10-16 02-49-15](https://github.com/user-attachments/assets/da16c8ce-2bf9-4251-9dd4-fee8d9a80faf)


### Shared Library structure

https://github.com/mygurukulam-p10/jenkins-shared-library.git

# Jenkinsfile
```

@Library("shared1") _  
node {
    try {
        // Git Checkout
        def branch = 'main'
        def creds = 'amit_cred'
        def url = 'git@github.com:mygurukulam-p10/employee-api.git'
        echo "Starting Git checkout on branch: ${branch} from URL: ${url} using credentials ID: ${creds}"
        gitCheckout(branch, creds, url)
        echo "Git checkout completed successfully."

        // Tool Installation
        def toolName = 'golang'
        goToolInstallation(toolName)  // Install Go tool

        // Snyk Test
        echo "Starting dependency scanning with Snyk..."
        GoDependencyScanning('snyk_token', 'snyk')  // Run Snyk dependency scanning
        echo "Dependency scanning completed successfully."

    } catch (Exception e) {
        echo "An error occurred: ${e.message}"
    }
}
```


## var folder groovy files
goInstallDependency.groovy

```
def call (){
    stage("Install Dependencies") {
        // Use the Go tool to tidy dependencies
        sh "go mod tidy"
    }
}
```


gitCheckout.groovy
```
def call (String branch, String creds, String url) {
        stage('Checkout') {
            // Perform the Git checkout
            script{

                git branch: "${branch}", url: "${url}", credentialsId: "${creds}"
            }
            
        }
        return "Checkout successful for branch: ${branch}"
    }
```


GoDependencyScanning.groovy

```
def call(String  snykTokenId , String snykInstallation){

        stage("Run snyk test"){
           script{
          snykSecurity(
          snykInstallation: snykInstallation,
          snykTokenId: snykTokenId)

           }
            
        }

        return "testing done"
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

