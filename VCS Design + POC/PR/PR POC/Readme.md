# Pull Request POC ![git-pull-request-fill-development](https://github.com/user-attachments/assets/047edfc3-5555-448c-ac53-ebb5d81207ba)

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 09-09-24    | version 1  | Megha Tyagi     | 10-09-24       |

## Purpose
The purpose of this POC document is to outline the necessary steps and procedures for creating a Pull Request (PR). This document aims to provide a comprehensive understanding of the PR process, including the rationale behind the proposed changes, how to implement them effectively, and the benefits they bring to the project. 

## Table of Contents
1. [PR Work Flow](#pr-work-flow)
2. [Pre-requisites](#pre-requisites)
3. [Step-by-Step Guide to Create a Pull Request (PR)](#step-by-step-guide-to-create-a-pull-request-pr)



## PR Work Flow
   ![pull-request-flow](https://github.com/user-attachments/assets/b22e6c8e-dd66-4f03-9683-527d63ef8624)


## Pre-requisites
Before proceeding with the Proof of Concept (POC) for creating a Pull Request (PR), ensure the following prerequisites are met:
**GitHub Account**: A GitHub account is required to create and manage Pull Requests. Ensure that you have an active GitHub account and necessary permissions for the repository you are working on.

## Step-by-Step Guide to Create a Pull Request (PR)
Creating a Pull Request (PR) involves several steps to propose changes to a repository. Here’s a detailed guide to help you through the process:
1. **Create Repository in git and add the project file**
   - Log in to your Git platform (e.g., GitHub).
   - Navigate to the Repositories section and click on New.
   - Enter a repository name, select its visibility (public or private), and add a description if needed.
   - Click Create Repository. This initializes an empty repository on the Git platform.

     <img width="941" alt="create repo" src="https://github.com/user-attachments/assets/701c768b-a12a-4bcc-b603-bfe1c2f4113d">
  
     ![create file](https://github.com/user-attachments/assets/57d34213-1ab9-40db-bad9-39260245bf98)


2. **After adding the project files, clone the repository to your local system to continue with further development and version control activities.**
   
   ```
   git clone https://github.com/mygurukulam-p10/PR-Demo-Repo.git
   ```
   <img width="595" alt="Git Clone repo in local machine" src="https://github.com/user-attachments/assets/fc447a26-5468-4053-a5d7-c9d6688fd6e5">

3. **Changes the directory into private.**
   ```
   cd <directory name>
   ```
4. **Create a new branch to implement changes in the project code using the command below.**
 ```
 git checkout -b new_branch
 ```
   <img width="425" alt="Create a New branch" src="https://github.com/user-attachments/assets/b7086552-0c7f-499e-8789-f949036ef44c">


5. **Switch to the new branch using the `git branch` command.**
   
   <img width="376" alt="switch to new branch" src="https://github.com/user-attachments/assets/d5bf80c3-892c-4fec-a9f3-b93390d42c1a">

6. **Make the changes in project file with command**
   ```
   vi <file name>
   ```
   <img width="651" alt="changes in file" src="https://github.com/user-attachments/assets/fe64a5ba-67d7-499d-bc6f-a58749eb1839">

7. **With the help of below mentioned command we can see the modified change in project file**
   ```
   git status
   ```
   <img width="451" alt="git status" src="https://github.com/user-attachments/assets/e8f9ae39-2553-44bb-b528-414718c10f1e">

8. **Next, stage your changes using the command provided below.**
   ```
   git add <file name"
   ```
   <img width="446" alt="git add " src="https://github.com/user-attachments/assets/a17530f4-e87a-43d4-a51d-63e4373ce8fe">

9. **Then commit our stage change with given command**
    ```
    git commit -m "message of change file"
    ```
    <img width="521" alt="git commit with updated file" src="https://github.com/user-attachments/assets/c382ca63-1d05-410c-8094-e16308141add">

10. **Now push our code back to git hub with this command & Uploads the changes from your local new_branch to the remote repository.**
    ```
    git push --set-upstream origin new_branch
    ```
   <img width="649" alt="git push new branch in git" src="https://github.com/user-attachments/assets/c9efce6d-c954-44b6-b5ec-4674b0898de7">

11. **Now go back to your GitHub repo and we can see that new branch is now recognized**
    ![see new branch](https://github.com/user-attachments/assets/ff55a79f-c14a-465e-8eaa-f6ae9f113f58)

12. **Firstly go the pull request and create new pull request**
   ![create new pull request](https://github.com/user-attachments/assets/5f363732-7038-4fda-aa82-f4ecda1e67f0)

13. **On the right side we select the branch which we gonna merge**
   ![base and comapre branch](https://github.com/user-attachments/assets/3f19c3bd-5429-46f3-8b67-7fe43f329d27)

14. **Create Pull request and at this tim you can update the name of the request and leave any comments**
    ![Leave comment](https://github.com/user-attachments/assets/078e929a-16f9-4651-97bd-d1e2590cb072)

15. **The check if any merge conflict after create the pull request, at this point out pull request is open and ready for review**
    ![check merge conflict](https://github.com/user-attachments/assets/732102cd-2522-4a2e-8a3b-3688265044da)
    <img width="941" alt="code changes review" src="https://github.com/user-attachments/assets/da9e8bc8-1eaa-421c-9348-f6086f844e1a">

16. **At the time of review we can add comment in review, if we want**
    ![review comment](https://github.com/user-attachments/assets/8507318b-66d9-4036-8b3e-74ff7744fbc5)
    
17. **After completing all the steps, the final task is to merge the code.**
    <img width="937" alt="merge the pull the request" src="https://github.com/user-attachments/assets/a4bfbf35-8001-4abc-b654-7e8c42c510d2">
    <img width="948" alt="merge successfull" src="https://github.com/user-attachments/assets/9507c840-0a4e-4caf-a6d4-edaa383ed257">

18. **Additionally,Once the changes have been successfully merged and are no longer needed, you can delete the branch you created for these changes.**
    



    



    
     

   

