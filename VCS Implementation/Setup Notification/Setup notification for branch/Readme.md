# <img width="35" alt="image" src="https://github.com/user-attachments/assets/cd1cb06d-90e7-410e-bccc-3a4d645dd6c5"> Setup notification for Branch


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  24-09-24   | Version 1  |    Megha Tyagi      | 24-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [🌟 Prerequisites](#-prerequisites)
3. [Steps to Set up Email Notificatin](#steps-to-set-up-email-notification)
4. [📜 Conclusion](#-conclusion)
5. [📚 References](#-references ) 
6. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
This document provides a clear guide for setting up notifications for branch events (create, delete, merge) in GitHub. By following these steps, users can stay informed about branch changes in their repositories. This helps improve team collaboration and keeps everyone updated on project progress.

![Untitled Diagram drawio (10)](https://github.com/user-attachments/assets/5bd94634-dd81-41e6-a01f-d25ab1bce438)


## 🌟 Prerequisites
- A GitHub account.
- Access to the repository for which you want to receive notifications.

##  Steps to Set up Email Notification

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.

<img width="451" alt="git account" src="https://github.com/user-attachments/assets/1326a269-ed1e-46a1-9bd4-4789d9272966">


### 2. Create a repository for which you want to configure notifications for Branch(Create,Delete& Merge).

<img width="451" alt="repo create" src="https://github.com/user-attachments/assets/7a49d439-bbdf-4ca4-8079-9ba78d5ddf73">


### 3. Now, click on the repository you created and navigate to the Settings tab at the top.

<img width="475" alt="Settings" src="https://github.com/user-attachments/assets/eb10a89f-7dd2-4d98-8758-601764aff506">


### 4. Generate an App Password for Gmail: If you are using Gmail, you'll need to generate an App Password for your Google account:

**Go to your Google Account.**

**Navigate to Security -> Signing in to Google -> App Passwords.**

**Choose Mail and select your device, then generate a password and copy it.**

<img width="469" alt="gmail password" src="https://github.com/user-attachments/assets/9a6b65b0-0e8f-4eea-a468-cfe0da7b99c8">


### 5. Add Gmail Credentials to GitHub Secrets:

**Go to your GitHub repository.** **Click on Settings -> Secrets -> Actions -> New repository secret,**Add two secrets:**

**EMAIL_USERNAME: Your Gmail address (e.g., your-email@gmail.com).**

**EMAIL_PASSWORD: The App Password you generated earlier from Gmail.**

<img width="944" alt="secrate password" src="https://github.com/user-attachments/assets/287c2b0e-ac36-4c2c-8d87-3d0a47e03bb5">


### 6. Set up GitHub Action Workflow:

**Create a GitHub Actions workflow file in your repository to send an email when a code commit is made.**

**In your GitHub repository, create a workflow file in .github/workflows/ (e.g., send-email-on-codecommit.yml):**

<img width="944" alt="workflow" src="https://github.com/user-attachments/assets/9af01505-d6cc-4462-a0ab-4a112bc942ee">


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



