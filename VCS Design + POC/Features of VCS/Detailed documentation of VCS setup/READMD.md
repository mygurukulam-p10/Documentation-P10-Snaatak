![1520202558864](https://github.com/user-attachments/assets/34b92e29-e69b-42b3-a553-2d6ed95afa3c)



# 🌟 VCS Setup Guide: Bitbucket, GitHub, and GitLab

This guide covers the setup process for popular Version Control Systems (VCS) – **Bitbucket**, **GitHub**, and **GitLab**. Each platform allows you to host, manage, and collaborate on code using Git. Let's walk through the setup for each platform, step by step.

---

## 📑 Table of Contents
- [Introduction](#introduction)
- [Bitbucket Setup](#bitbucket-setup)
- [GitHub Setup](#github-setup)
- [GitLab Setup](#gitlab-setup)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

---

## 🔧 Introduction

Version Control Systems like **Bitbucket**, **GitHub**, and **GitLab** provide essential tools to track changes in your code, collaborate with others, and manage repositories effectively. This guide provides a simple, step-by-step process to get started with each platform.

---

## 🧰 Bitbucket Setup

**Bitbucket** by Atlassian is known for integrating well with tools like Jira and Trello. It allows you to manage Git repositories and collaborate on code.

### Steps to Set Up Bitbucket:
1. **Create an Account**: Go to [Bitbucket](https://bitbucket.org/) and sign up for a free account.
2. **Create a Repository**:
   - Click on **Repositories** in the top navigation bar.
   - Select **Create Repository**.
   - Choose a project name, repository name, and set it to **private** or **public**.
3. **Set Git Username and Email**:
    This configures Git to associate your commits with a username and email.
 ```
   git config --global user.name "brijsingh21"
   git config --global user.email "brij.singh.snaatak@mygurukulam.co"
   ```
4. **Clone the Repository**:
   - Once created, you will see the clone URL. Use the following Git command to clone it locally:
     ```bash
     git clone https://bitbucket.org/username/repository_name.git
     ```
5. **Push Your Code**:
   - After making changes, use the following commands to push your code:
     ```bash
     git add .
     git commit -m "Initial commit"
     git push origin main
     ```

6. **Collaborate**: Invite team members by going to the repository settings and selecting **User and Group Access**.

---

## 🐙 GitHub Setup

**GitHub** is one of the most popular Git hosting platforms used by millions of developers and open-source projects.

### Steps to Set Up GitHub:
1. **Create an Account**: Visit [GitHub](https://github.com/) and sign up.
2. **Create a New Repository**:
   - Click on the **New** button in the repositories section.
   - Add a **repository name**, select public or private, and optionally add a README.
3. **Set Git Username and Email**:
    This configures Git to associate your commits with a username and email.
 ```
   git config --global user.name "brijsingh21"
   git config --global user.email "brij.singh.snaatak@mygurukulam.co"
   ```
4. **Clone the Repository**:
   - Copy the HTTPS or SSH link and clone it:
     ```bash
     git clone https://github.com/username/repository_name.git
     ```
5. **Push Your Code**:
   - After making changes, push your code with the following commands:
     ```bash
     git add .
     git commit -m "Initial commit"
     git push origin main
     ```

6. **Collaborate**: To collaborate, go to **Settings > Manage access** and invite your team.

---

## 🦊 GitLab Setup

**GitLab** offers a full DevOps platform, including Git repository hosting, CI/CD, and security scanning tools.

### Steps to Set Up GitLab:
1. **Sign Up**: Head to [GitLab](https://gitlab.com/) and create an account.
2. **Create a New Project**:
   - Go to the **Projects** tab and click **New Project**.
   - Choose between creating a **blank project**, importing an existing one, or using a template.
3. **Set Git Username and Email**:
    This configures Git to associate your commits with a username and email.
 ```
   git config --global user.name "brijsingh21"
   git config --global user.email "brij.singh.snaatak@mygurukulam.co"
   ```
4. **Clone the Repository**:
   - Once the repository is created, clone it using the following Git command:
     ```bash
     git clone https://gitlab.com/username/repository_name.git
     ```
5. **Push Your Code**:
   - Use the following Git commands to push code:
     ```bash
     git add .
     git commit -m "Initial commit"
     git push origin main
     ```

6. **Collaborate**: Navigate to the **Members** section under **Settings** and invite collaborators to your project.

---

## 📝 Conclusion

Setting up a version control system on platforms like **Bitbucket**, **GitHub**, and **GitLab** is a straightforward process. These platforms offer robust tools for code management, collaboration, and deployment pipelines. Whether you choose Bitbucket for its Jira integration, GitHub for its open-source community, or GitLab for its DevOps features, each platform provides a scalable and efficient way to manage your code.

---

## 📧 Contact Information

For further assistance or questions, feel free to contact:

| Name         | Email Address                      |
|--------------|------------------------------------|
| Brij Singh   | brij.singh.snaatak@mygurukulam.co  |

---

## 📚 References

- [Bitbucket Documentation](https://support.atlassian.com/bitbucket-cloud/)
- [GitHub Documentation](https://docs.github.com/)
- [GitLab Documentation](https://docs.gitlab.com/)
- [Git Basics: Getting Started with Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

