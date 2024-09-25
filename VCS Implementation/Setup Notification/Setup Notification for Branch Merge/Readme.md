# <img width="33" alt="image" src="https://github.com/user-attachments/assets/f4828f0f-f961-4939-8219-90e2a0f86544"> Setup notification for Branch


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  25-09-24   | Version 1  |    Megha Tyagi      | 25-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [🌟 Prerequisites](#-prerequisites)
3. [Steps to Set up Branch Notificatin](#steps-to-set-up-email-notification)
4. [📜 Conclusion](#-conclusion)
5. [📚 References](#-references ) 
6. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
This document provides a clear guide for setting up notifications for branch events (create, delete, merge) in GitHub. By following these steps, users can stay informed about branch changes in their repositories. This helps improve team collaboration and keeps everyone updated on project progress.

![Untitled Diagram drawio (10)](https://github.com/user-attachments/assets/5bd94634-dd81-41e6-a01f-d25ab1bce438)


## 🌟 Prerequisites
- A GitHub account.
- Access to the repository for which you want to receive notifications.

##  Steps to Set up Branch Notification

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.

<img width="451" alt="git account" src="https://github.com/user-attachments/assets/1326a269-ed1e-46a1-9bd4-4789d9272966">


### 2. Create a repository for which you want to configure notifications for Branch Merge.

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

![Screenshot 2024-09-25 114351](https://github.com/user-attachments/assets/835f8694-5d1c-48ed-9f5a-5c61638c57c1)



### 6. Set up GitHub Action Workflow:

**Create a GitHub Actions workflow file in your repository to send an email when a Branch- create, Merge & Delete.**

**In your GitHub repository, create a workflow file in .github/workflows/ (e.g., send-email-on-Branch-notification.yml):**

<img width="927" alt="workflow" src="https://github.com/user-attachments/assets/6313e88a-999f-4136-bbb2-195d6d8913b9">



### 7. Commit and Push the Workflow File:

**Once you add the workflow file, every time a commit is pushed to the specified repo (e.g., Branch-Notification-demo), the GitHub Action will send an email with the details of the commit (message, author, and URL).**

<img width="664" alt="new branch create" src="https://github.com/user-attachments/assets/961c4fd7-fb09-4444-9c9d-927660751ff3">

![Screenshot 2024-09-25 121553](https://github.com/user-attachments/assets/18ac33ad-5353-40e7-80bd-9d90a8f26337)

![Screenshot 2024-09-25 122033](https://github.com/user-attachments/assets/07b5f485-1db6-4171-bb51-cd0b3375024d)


<img width="464" alt="create a new branch" src="https://github.com/user-attachments/assets/b065ed81-2eb7-415f-8112-d63ee0bcebbd">


<img width="463" alt="branch merge" src="https://github.com/user-attachments/assets/8a805dfb-ca35-46eb-a6b6-480ca572e7d2">


<img width="463" alt="branch delete" src="https://github.com/user-attachments/assets/0b84b8e9-dca1-4125-a48d-5c95487d467f">


## 📜 Conclusion
The POC successfully implements an email notification system that triggers on critical branch events: creation, deletion, and merging of branches in a GitHub repository. It leverages GitHub Actions to automatically send notifications, ensuring that team members are promptly informed of important branch activities, enhancing collaboration and workflow monitoring.
 
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




