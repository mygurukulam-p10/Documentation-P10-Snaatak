# <img width="35" alt="image" src="https://github.com/user-attachments/assets/cd1cb06d-90e7-410e-bccc-3a4d645dd6c5"> Setup notification for Code commit


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  23-09-24   | Version 1  |    Megha Tyagi      | 23-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [Workflow](#workflow)
3. [🌟 Pre-requisites](#-pre-requisites)
4. [Steps to Set up Email Notificatin](#steps-to-set-up-email-notification)
5. [📜 Conclusion](#-conclusion)
6. [📚 References](#-references ) 
7. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
This document provides a clear, step-by-step guide for setting up email notifications for code commits in GitHub. By following these instructions, users can stay informed about changes in their repositories without requiring any scripting or complex configurations. This enhances collaboration and keeps team members updated on project developments.

## Workflow
![codecommit drawio (2)](https://github.com/user-attachments/assets/93433a96-f1ff-45a3-b38d-a198555dcf9a)

## 🌟 Pre-requisites
- A GitHub account.
- Access to the repository for which you want to receive notifications.

##  Steps to Set up Email Notification

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.

<img width="958" alt="image" src="https://github.com/user-attachments/assets/d6acff0d-0562-441c-813c-37cfbe5ebeec">

### 2. Create a repository for which you want to configure notifications for code commits.

![Screenshot 2024-09-23 164450](https://github.com/user-attachments/assets/7488354d-04a7-4d07-8d28-6003db689937)

### 3. Now, click on the repository you created and navigate to the Settings tab at the top.

![Screenshot 2024-09-23 173912](https://github.com/user-attachments/assets/1aef0657-d0c8-48b0-9455-da153bc2c312)

### 4. Generate an App Password for Gmail: If you are using Gmail, you'll need to generate an App Password for your Google account:

**Go to your Google Account.**

**Navigate to Security -> Signing in to Google -> App Passwords.**

**Choose Mail and select your device, then generate a password and copy it.**

![Screenshot 2024-09-23 200443](https://github.com/user-attachments/assets/065d60fb-63ab-4ed6-a9d9-449425c6238a)

### 5. Set up GitHub Action Workflow:

**Create a GitHub Actions workflow file in your repository to send an email when a code commit is made.**

**In your GitHub repository, create a workflow file in .github/workflows/ (e.g., send-email-on-codecommit.yml):**

![Screenshot 2024-09-23 200921](https://github.com/user-attachments/assets/e2b44183-c3ca-4533-aff7-c0643f904076)

### 6. Add Gmail Credentials to GitHub Secrets:

**Go to your GitHub repository.**

**Click on Settings -> Secrets -> Actions -> New repository secret.**

**Add two secrets:**

**EMAIL_USERNAME: Your Gmail address (e.g., your-email@gmail.com).**

**EMAIL_PASSWORD: The App Password you generated earlier from Gmail.**

![Screenshot 2024-09-23 200808](https://github.com/user-attachments/assets/8b99b2d8-13b6-4b91-b2bd-52ffc6b12f10)

### 7. Commit and Push the Workflow File:

**Once you add the workflow file, every time a commit is pushed to the specified repo (e.g., code-commit-demo), the GitHub Action will send an email with the details of the commit (message, author, and URL).**

![Screenshot 2024-09-23 235555](https://github.com/user-attachments/assets/8121b4ce-16f5-4847-ab52-0579bc8b8307)

![Screenshot 2024-09-23 202553](https://github.com/user-attachments/assets/4c1b23ab-c3b5-41a7-9851-a4519a3fcaeb)

![Screenshot 2024-09-23 201433](https://github.com/user-attachments/assets/b0d72001-5fa1-4951-a1a8-6dbba9e674d5)

![Screenshot 2024-09-23 201420](https://github.com/user-attachments/assets/04cb5dc1-14c0-4347-9852-aca8fcc78635)

![Screenshot 2024-09-23 201803](https://github.com/user-attachments/assets/1351519b-17b9-4374-b279-90234bc27916)


## 📜 Conclusion
The POC successfully demonstrates an automated email notification system for new code commits, in a GitHub repository. It uses GitHub Actions and a secure email integration via Gmail credentials. This solution ensures timely notifications for relevant code changes while filtering out unnecessary merge events.
 
## 📚 References 
|links | Description |
|-------|------------|
|https://youtu.be/oMU9MUIXPyI?feature=shared|**Rainbow talks** |
|https://www.youtube.com/watch?v=qToZN5S67AM| **SDet Automation**|
|https://tinyurl.com/bdpf3ajc|**GIT**|

## 📧 Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Megha Tyagi**|megha.tyagi.snaatak@mygurukulam.co|


