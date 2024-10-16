# Code Compilation

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | Last Update                    |
|--------------------|------------|--------------|--------------------------------|
| 04-10-2024         | 1.0      | Aayush Gaur  | 16-10-2024           |


## Introduction
Automating the process of building and deploying Go applications can be efficiently done using Continuous Integration (CI) pipelines. Declarative Pipelines in Jenkins allow for structured and readable automation scripts, making the entire Go code compilation process easier to manage and understand.

## Pre-requisites
Before starting, make sure you have the following tools:
1. **Jenkins**: Ensure you have a Jenkins instance running.
2. **Go Plugin**: Ensure you have Go Plugin is configured.

## Plugin Setup - Go Plugin
### Step 1: Search for the Go Plugin & Install
![Screenshot from 2024-10-04 14-34-50](https://github.com/user-attachments/assets/8d0375aa-0c41-45a5-b3a8-6ced03e1943b)

### Step 2: Configure Go in Jenkins
![Screenshot from 2024-10-04 14-40-27](https://github.com/user-attachments/assets/03a80c25-3980-4baa-9e32-08ff4bf7d092)

## Code Compilation Setup

### Step 1: Create a New Pipeline Job
- In the Jenkins dashboard, click New Item.
- Name your job (e.g., "GoLang Code Compilation").
- Select Pipeline and click OK.
![Screenshot from 2024-10-16 13-14-55](https://github.com/user-attachments/assets/178ffbf7-c36c-4fb8-8408-9c58e945ee44)


### Step 2: Configure the Pipeline Script
- In the job configuration, scroll to the Pipeline section.
- Choose Pipeline script from SCM.
- Enter your GitHub repository URL and credentials.
![Screenshot from 2024-10-16 13-15-57](https://github.com/user-attachments/assets/ddb2012d-a4a8-4310-add9-76dcd61cf3df)
![Screenshot from 2024-10-16 13-16-17](https://github.com/user-attachments/assets/84c206d5-0296-4718-8fc8-b1e628353169)



### Step 3: Save the Configuration
- Click Save to save the pipeline settings.

### Step 4: Trigger the Build
- Go back to your Jenkins job and click Build Now to run the pipeline.

### Step 5: View Build Output
- After starting the build, click on the build number to see the console output.
- This will show you each step, including Go code checkout and compilation.

### 5. 🚀 Click on Build to run the pipeline for Code Compilation.
![Screenshot from 2024-10-16 14-31-58](https://github.com/user-attachments/assets/9f752c6b-e02d-490d-a4d8-614108fc149e)


### 6. 🚀 Now, you should be able to see the build complete.
![Screenshot from 2024-10-16 15-45-53](https://github.com/user-attachments/assets/dc22a66f-c3ac-4860-b0cc-fedeb3eaf9cf)

### 7.🚀 Click on Console Output to see the complete build.
![Screenshot from 2024-10-16 15-47-19](https://github.com/user-attachments/assets/30ace96a-faab-4359-ad6d-19ca0dcbf781)
![Screenshot from 2024-10-16 15-48-11](https://github.com/user-attachments/assets/46259054-14ea-45f3-82f0-bd1f31f27b43)
![Screenshot from 2024-10-16 15-48-33](https://github.com/user-attachments/assets/8dd8e210-f5a6-4aec-9aaf-683a931ff627)



