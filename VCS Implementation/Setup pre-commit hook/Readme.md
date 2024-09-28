# Setup commit-hook  <img width="49" alt="image" src="https://github.com/user-attachments/assets/625f8c30-8c06-4eb0-be45-84696fc860f0">


---

| ✍️Author   | 📅Created on|📌 Version | 📝Last updated by   |📅 Last edited on |
|-------------|-------------|------------|---------------------|------------------|
| Megha Tyagi |  27-09-24   | Version 1  |    Megha Tyagi      | 27-09-24         |

---

# Table of Content 
1. [🔍 Purpose](#-purpose)
2. [🌟 Pre-Requisites](#-pre-requisites)
3. [🖥️ Steps to Set Up Commit Message Validation](#-steps-to-set-up-commit-message-validation)
4. [📜 Conclusion](#-conclusion)
5. [📚 References](#-references ) 
6. [📧 Contact Information ](#-contact-information )   
---
     
# 🔍 Purpose 
The purpose of this document is to outline the implementation of a Git commit message hook that ensures all commit messages contain valid JIRA ticket IDs. This practice enhances the clarity and traceability of code changes by directly linking them to specific tasks within the project management system. By enforcing this requirement, the hook fosters better communication among team members and ensures that every code change is documented with the appropriate context. Ultimately, this document serves as a guide for maintaining consistent and meaningful commit messages, facilitating a more organized development process.

## 🌟 Pre-requisites
- A GitHub account.

---
##  🖥️ Steps to Set Up Commit Message Validation

### 1. **Sign in to GitHub**: Go to [GitHub](https://github.com) and log in to your account.

<img width="674" alt="image" src="https://github.com/user-attachments/assets/b115f76a-1561-4a0d-9de5-f8263192f393">

### 2. Create a repository for which you want to configure notifications for code commits.

<img width="928" alt="image" src="https://github.com/user-attachments/assets/5ae07dd6-b83e-4c3d-9bb6-cf7438eea8db">

### 3. Clone the repository -

<img width="622" alt="Clone" src="https://github.com/user-attachments/assets/194baa11-3c47-4896-8a5c-8aec0af2eeb9">


### 4. Navigate to the Repository
```
cd<repo name>
```
<img width="544" alt="change Dir" src="https://github.com/user-attachments/assets/ee6ddc41-f4a6-48e1-8a57-fc73bd3384dd">

### 5. Create the Commit Message Hook
```
touch commit-msg
chmod +x commit-msg
```
<img width="625" alt="image" src="https://github.com/user-attachments/assets/4c993371-c5c6-4f2f-9b10-eadf2b97a3d0">

### 6. Open the commit-msg file and add the Validation Logic script to validate commit messages against a list of valid JIRA tickets:

<img width="794" alt="script for pre commit" src="https://github.com/user-attachments/assets/6bd9aff8-b6ef-43a0-9ab4-42b7d3d6d972">

### 7. Test the Hook
**After saving the hook, test it by attempting to commit changes with and without a valid JIRA ticket in the commit message:**
<img width="538" alt="unscussfull" src="https://github.com/user-attachments/assets/8a90b635-91c1-4102-8532-0dfd717dfa7f">
<img width="587" alt="commit successfull" src="https://github.com/user-attachments/assets/906c6867-35b8-4803-85e6-8f2d64918bd0">

---
## 📜 Conclusion
This document has outlined the process for implementing a Git commit message hook that requires commit messages to include valid JIRA ticket IDs. By enforcing this practice, teams can improve the traceability of changes, ensure better alignment with project management workflows, and enhance overall communication among team members. Consistent and meaningful commit messages contribute to a more organized development process, facilitating easier tracking of progress and accountability. Following the steps provided in this guide will help maintain high standards for documentation within your repository, ultimately leading to a more efficient and effective development environment.

---
## 📚 References 
|links | Description |
|-------|------------|
|https://devopedia.org/git-hooks|**Devopedia** |
|https://fredrkl.com/blog/git-pre-commit-hooks/| **Fredrik**|
|https://hydraulic.dev/blog/12-github-action.html|**Hydraulic**|

---
## 📧 Contact Information 
|Name|Email Address|
|:---:|:---:|
|**Megha Tyagi**|megha.tyagi.snaatak@mygurukulam.co|
