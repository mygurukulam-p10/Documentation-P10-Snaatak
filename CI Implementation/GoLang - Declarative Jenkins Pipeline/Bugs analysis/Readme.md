# Bus Analysis

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 04-10-2024         | 1.0      | Aayush Gaur  |   Bus Analysis   |

## Introduction
This document outlines how to set up a Declarative Jenkins Pipeline specifically for Go-Lang Bugs analysis. Jenkins, as a popular automation server, supports a variety of build configurations.

## Pre-requisites
- Jenkins: Ensure you have a Jenkins instance running.
- golang: Make sure GoLang is installed on the machine where Jenkins agents are running.
- golangCI-lint: Install a GoLang bug analysis tool like golangci-lint

## Step to Setup
### Step 1: Create a New Pipeline Job:
- Navigate to the Jenkins dashboard and click on New Item.
- Enter a name for your job ex, Go bug-analysis
![Screenshot from 2024-10-10 15-04-19](https://github.com/user-attachments/assets/5f35bb05-ea0e-40f3-a902-9d985fa44b7a)

### Step 2: Configure the Pipeline Script
- In the job configuration, scroll to the Pipeline section.
- Choose Pipeline script from SCM.
- Enter your GitHub repository URL and credentials.
![Screenshot from 2024-10-24 15-05-37](https://github.com/user-attachments/assets/9efb62da-a2db-4215-a7eb-9c7cb0f00cc7)
![Screenshot from 2024-10-24 15-05-44](https://github.com/user-attachments/assets/46174563-c9c4-4cbb-9994-8b21b72712e3)

### Step 3: Trigger the Build
- Go back to your Jenkins job and click Build Now to run the pipeline.

### Step 4: Now, you should be able to see the build complete.

### Step 5: Click on Console Output to see the complete build.
