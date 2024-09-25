# <img width="33" alt="image" src="https://github.com/user-attachments/assets/f4828f0f-f961-4939-8219-90e2a0f86544"> Setup notification for Branch Merge


| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  25-09-24   | Version 1  |    Megha Tyagi      | 25-09-24         |



# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [Workflow](#workflow)
3. [🌟 Pre requisites](#-pre-requisites)
4. [Steps to Set up Branch Merging Notificatin](#steps-to-set-up-branch-merging-notification)
5. [📜 Conclusion](#-conclusion)
6. [📚 References](#-references ) 
7. [📧 Contact Information ](#-contact-information )
   

     
# 🔍 Purpose 
This document provides a clear guide for setting up notifications for branch Merging events in GitHub. By following these steps, users can stay informed about branch Merging in their repositories. This helps improve team collaboration and keeps everyone updated on project progress.


# Workflow

![BranchMerge drawio](https://github.com/user-attachments/assets/c2a33fdf-e42a-4116-ad10-ec6346069578)


# 🌟 Pre-requisites
- A GitHub account.
- Access to the repository for which you want to receive notifications.

#  Steps to Set up Branch Merging Notification

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.

![image](https://github.com/user-attachments/assets/90deb434-b203-40a8-b1b0-9246c78751c1)


### 2. Create a repository for which you want to configure notifications for Branch Merge.

<img width="941" alt="image" src="https://github.com/user-attachments/assets/fc6628f0-6490-4be8-bcd4-468c17c87c36">


### 3. Now, click on the repository you created and navigate to the Settings tab at the top.

<img width="941" alt="image" src="https://github.com/user-attachments/assets/92f65faf-9314-4610-b4c7-dd7ec910d7a3">


### 4. Generate an App Password for Gmail: If you are using Gmail, you'll need to generate an App Password for your Google account:

**Go to your Google Account.**

**Navigate to Security -> Signing in to Google -> App Passwords.**

**Choose Mail and select your device, then generate a password and copy it.**

![for scerate password](https://github.com/user-attachments/assets/2eb0cdfd-be36-47fa-bce4-8f9011e89e35)



### 5. Add Gmail Credentials to GitHub Secrets:

**Go to your GitHub repository.** **Click on Settings -> Secrets -> Actions -> New repository secret,**Add two secrets:**

**EMAIL_USERNAME: Your Gmail address (e.g., your-email@gmail.com).**

**EMAIL_PASSWORD: The App Password you generated earlier from Gmail.**

<img width="942" alt="image" src="https://github.com/user-attachments/assets/ae706d0c-dc40-4706-9bc6-480301232dbf">




### 6. Set up GitHub Action Workflow:

**Create a GitHub Actions workflow file in your repository to send an email when a Branch- create, Merge & Delete.**

**In your GitHub repository, create a workflow file in .github/workflows/ (e.g., send-email-on-Branch-notification.yml):**

<img width="929" alt="image" src="https://github.com/user-attachments/assets/b4d55ffe-1950-4947-9fed-41637491a0ee">




### 7. Commit and Push the Workflow File:

**Once you add the workflow file, every time a commit is pushed to the specified repo (e.g., Branch-Notification-demo), the GitHub Action will send an email with the details of the commit (message, author, and URL).**

<img width="629" alt="image" src="https://github.com/user-attachments/assets/177f9db4-a4b7-4031-bbd9-86e65d94e53c">

<img width="943" alt="image" src="https://github.com/user-attachments/assets/48ee9352-06d8-49e9-83f8-b73a5b2aa771">



# 📜 Conclusion
The POC successfully implements an email notification system that triggers on critical branch events: creation, deletion, and merging of branches in a GitHub repository. It leverages GitHub Actions to automatically send notifications, ensuring that team members are promptly informed of important branch activities, enhancing collaboration and workflow monitoring.
 
# 📚 References 
|links | Description |
|-------|------------|
|https://youtu.be/oMU9MUIXPyI?feature=shared|**Rainbow talks** |
|https://www.youtube.com/watch?v=qToZN5S67AM| **SDet Automation**|
|https://tinyurl.com/bdpf3ajc|**GIT**|

# 📧 Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Megha Tyagi**|megha.tyagi.snaatak@mygurukulam.co|




