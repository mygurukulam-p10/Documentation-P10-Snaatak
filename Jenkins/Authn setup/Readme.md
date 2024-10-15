
# 🛡️ Authentication in Jenkins

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 06-09-2024         | 0.2        | Brij Singh   | Documentation on Salary API    |

## 📋 Table of Contents
1. [Introduction](#introduction)
2. [What is Authentication in Jenkins?](#what-is-authentication-in-jenkins)
3. [Why is Authentication Important?](#why-is-authentication-important)
4. [Authentication Methods](#authentication-methods)
5. [Limitations](#limitations)
6. [Best Practices](#best-practices)
7. [Types of Authentication in Jenkins](#types-of-authentication-in-jenkins)
8. [POC: Setting up Authentication](#poc-setting-up-authentication)
9. [Conclusion](#conclusion)
10. [Contact Information](#contact-information)
11. [References](#references)

---

## 🔍 Introduction

This document gives an overview of how authentication works in Jenkins. Jenkins is an open-source server that helps automate building, testing, and deploying software. To keep Jenkins safe, it uses **authentication** (to verify user identity) and **authorization** (to control what users can do).

---

## ❓ What is Authentication in Jenkins?

Authentication is about checking who a user is. In Jenkins, users must authenticate (prove who they are) to access or interact with the Jenkins server.

---

## 🛡️ Why is Authentication Important?

| Reason                          | Explanation |
|----------------------------------|-------------|
| **Security**                     | Makes sure only the right people access Jenkins. |
| **Control Access**               | Ensures users can only see and do what they are allowed to. |
| **Auditing and Tracking**        | Logs user actions for tracking and troubleshooting. |
| **Integration with Other Tools** | Allows Jenkins to securely interact with external tools. |
| **Compliance**                   | Helps meet security requirements and standards. |

---

## 🔑 Authentication Methods

Jenkins has several ways to handle user login:

| Method                           | Description |
|-----------------------------------|-------------|
| **Jenkins Database**              |Jenkins manages usernames and passwords internally.
Example: A user logs into Jenkins with credentials (username: "dev_user", password: "dev_pass") stored in Jenkins. |
| **LDAP (e.g., Active Directory)** | Jenkins integrates with corporate LDAP, allowing employees to use their existing work credentials.
Example: An employee logs into Jenkins with their company email and password (stored in the company’s Active Directory).|
| **Single Sign-On (SSO)**          |Allows users to log in once and access multiple systems using SAML or OAuth.
Example: A user logs into Jenkins via their Google Workspace account, which also grants them access to other company services.|
| **API Token**                     |Jenkins users can generate API tokens for programmatic access, instead of using passwords.
Example: A user creates an API token in Jenkins and uses it to trigger Jenkins builds via a script or command-line tool. |
| **SSH Keys**                      | Used for secure logins, often with Git integration, bypassing passwords.
Example: A developer configures Jenkins to log in using their public SSH key, which they also use for Git operations|


---

## ⚠️ Limitations

| Limitation            | Explanation |
|-----------------------|-------------|
| **Limited Integration**| Jenkins’ built-in database is not always the best for large teams. |
| **Scalability**        | Larger companies may need more scalable authentication methods like LDAP or SAML. |
| **Security**           | External providers often offer stronger, centralized security. |

---

## 💡 Best Practices

To keep Jenkins secure, follow these tips:

| Practice                          | Description |
|------------------------------------|-------------|
| **Use Strong Passwords**           | Require complex passwords to improve security. |
| **Enable Multi-Factor Authentication** | Add another layer of security with MFA. |
| **Rotate Credentials Regularly**   | Change passwords and tokens frequently. |
| **Limit User Privileges**          | Only give users the permissions they need. |
| **Monitor User Activity**          | Keep an eye on logs for suspicious behavior. |
| **Update Jenkins and Plugins**     | Regularly update Jenkins to keep it secure. |


---

## 🧪 POC: Setting up Authentication

### 1. Install GitHub Authentication Plugin
- Go to **Manage Jenkins** > **Manage Plugins**.
  ![image](https://github.com/user-attachments/assets/41758104-dd3f-4344-b4a4-c0caba44c605)
![image](https://github.com/user-attachments/assets/68664af8-b2e7-47fe-8e6d-c8ea39a71d2a)

- Search for and install **GitHub Authentication Plugin**.
  ![image](https://github.com/user-attachments/assets/5c1c07aa-c225-4efb-8884-2d172ab4019d)
![image](https://github.com/user-attachments/assets/b91535db-a253-41a5-9fab-3acfc0d5f475)


### 2. Configure GitHub Authentication
After installing the plugin, go back to the Jenkins dashboard
**Click on "Manage Jenkins" again**
![image](https://github.com/user-attachments/assets/2013290b-96f9-4c6d-939e-ce043618d307)

**Select "Configure Global Security**

![image](https://github.com/user-attachments/assets/c0e36b51-0ad9-48fb-9ce9-d80b15badd0f)

**Setting Up an Application in GitHub**

Once you have installed the GitHub authentication plugin, you need to set up an application within GitHub. Here’s how:

*Log into your GitHub account.*

![image](https://github.com/user-attachments/assets/04c3dd6f-e5d1-4017-985e-61d88e14fa82)

**Scroll to the bottom of the page and click on “Developer settings”.**

![image](https://github.com/user-attachments/assets/f81854cc-76db-428d-b37e-d8d78c0acb12)  ![image](https://github.com/user-attachments/assets/4025766d-6b63-41f7-b082-e65a3f4743f0)




**Click on “OAuth Apps” and then on “Register a new application”.**

![image](https://github.com/user-attachments/assets/36d7b245-bd3a-4293-b1f2-df48e75d49d1)

**Install the GitHub Authentication Plugin in Jenkins**

A.Go to your Jenkins dashboard.

B.Click on Manage Jenkins > Manage Plugins.

![image](https://github.com/user-attachments/assets/24a69e4c-15fa-4ca2-bcca-ed95d8fbae3c)

C.Search for GitHub Authentication Plugin under the "Available" tab.

D. Install the plugin and restart Jenkins if required.
![image](https://github.com/user-attachments/assets/1276a311-215e-4fa8-b743-f428e7fadb77)

****3. Configure GitHub OAuth in Jenkins****

**A.Go to Manage Jenkins > Configure Global Security**

![image](https://github.com/user-attachments/assets/3e65dab8-b26a-4df5-9752-bc39f3eb274b)

**B.Under Security Realm, select GitHub Authentication**

![image](https://github.com/user-attachments/assets/4409e104-300f-45c4-bf08-d96a969a8883)

**C.Enter the Client ID and Client Secret that you obtained from GitHub when creating the OAuth App.**

![image](https://github.com/user-attachments/assets/d2b668eb-8a54-41d6-a7d0-e9a235135b1e)


**D.For GitHub Web URI, set https://github.com and For GitHub API URI, set https://api.github.com.**


![image](https://github.com/user-attachments/assets/2b412fdd-801c-49d7-b85c-543a8cd6070b)



****Save and Test the Integration:****

**Save the settings and go to the Jenkins login page.**

You should see the option to Login with GitHub.

**Click on the button, and you will be redirected to GitHub to authorize Jenkins**

![image](https://github.com/user-attachments/assets/9a103c97-4f1c-4c0b-b20d-06cb31b43355)

After granting access, you will be logged into Jenkins using your GitHub credentials.

![image](https://github.com/user-attachments/assets/6f114c5d-2dbb-4a75-abb6-d954c1a6f0aa)


![image](https://github.com/user-attachments/assets/c58f6f5d-d9c0-4a73-bbc0-4b8d4d40ea07)

---

## 📌 Conclusion

Jenkins offers many ways to authenticate users, from using its built-in database to integrating with external providers like LDAP or SAML. The best method depends on the size of your team and the security requirements of your organization.

---

## 📧 Contact Information

For any queries or further information, feel free to contact:

| 📛 Name       | ✉️ Email Address                    |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |

---

## 📚 References

| Link | Description |
|------|-------------|
| [Jenkins Documentation](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) | Jenkins Application Template |
| [GitHub OAuth Setup](https://stackoverflow.com/questions/60559456/configuring-jenkins-with-github-authorization) | Guide to setting up GitHub OAuth |




