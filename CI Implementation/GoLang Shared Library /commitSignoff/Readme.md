# Commit Sign-Off - Jenkins Shared Pipeline with Email Notification and Parameterization

---

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 17-10-2024      | Version 2    | Amit Nagar         | 17-10-2024        |             |             |             |

---

## Table of Contents

1. [💥 Introduction](#-introduction)
2. [⚙️ Prerequisites](#-prerequisites)
3. [🔍 System Requirements](#-system-requirements)
4. [💥 Steps to Configuration for Commit Sign-Off with Email Notification](#-steps-to-configuration-for-commit-sign-off-with-email-notification)
5. [Jenkinsfile](#jenkinsfile)
6. [📛 Conclusion](#-conclusion)
7. [📧 Contact Information](#-contact-information)
8. [📚 References](#-references)

---

## ⭐ Introduction 
This document outlines how to configure a Jenkins shared pipeline that enforces commit sign-off, sends email notifications for failures, and includes parameterization for flexibility.

---

## ⚙️ Prerequisites

| Requirement          | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| **✔️ Jenkins**        | Jenkins installed and configured for CI/CD processes.                       |
| **✔️ Git**            | Git must be installed on the Jenkins server for repository checkout.        |
| **✔️ Git Credentials**| Add your GitHub credentials (e.g., git-token) in Jenkins for repository access. |
| **✔️ Email**          | SMTP configuration for sending emails from Jenkins.                         |

---

## 🔍 System Requirements

### Hardware System Requirements

| Requirement          | Specification                                                     |
|----------------------|-------------------------------------------------------------------|
| **Processor**        | Minimum 2-core CPU                                                |
| **Memory (RAM)**     | Minimum 4 GB                                                      |
| **Storage**          | Minimum 20 GB                                                     |
| **Operating System** | Ubuntu 22.04                                                      |

---

## 💥 Steps to Configuration for Commit Sign-Off with Email Notification

Reference link to follow steps (#https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/CI%20Implementation/GoLang%20Shared%20Library%20/Dependency%20scanning/Unit-Tesing)

---

## Jenkinsfile

This pipeline does the following:
1. Checks if commits are signed off.
2. Sends an email if commits are missing a sign-off.
3. Allows the Git branch and recipient email to be parameterized.



