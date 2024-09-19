# Jenkins Log Files

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 20-09-2024         | 0.1       | Brij Singh   | Log Files         |

## 📘 Introduction
Jenkins is an open-source automation server used for Continuous Integration and Continuous Deployment (CI/CD). In the process of running builds, jobs, and various tasks, Jenkins generates multiple log files. These logs provide insights into Jenkins operations, job execution, errors, and system activity, which are essential for debugging and monitoring.

This document details the various types of log files generated in Jenkins, where they are located, and their purpose.

## 🗂️ Table of Contents
- [What are Jenkins Log Files?](#what-are-jenkins-log-files)
- [Why are Jenkins Logs Important?](#why-are-jenkins-logs-important)
- [Types of Log Files in Jenkins](#types-of-log-files-in-jenkins)
  - [1. System Logs](#1-system-logs)
  - [2. Build Logs](#2-build-logs)
  - [3. Node Logs](#3-node-logs)
  - [4. Plugin Logs](#4-plugin-logs)
  - [5. Access Logs](#5-access-logs)
- [How to Access Jenkins Logs](#how-to-access-jenkins-logs)
- [Best Practices for Managing Logs](#best-practices-for-managing-logs)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

## ❓ What are Jenkins Log Files?
**Jenkins log files** are records of Jenkins system activities, job executions, and errors. They provide a detailed account of what happens during the operation of Jenkins. Logs help administrators and developers monitor Jenkins performance, troubleshoot errors, and optimize CI/CD pipelines.

## 💡 Why are Jenkins Logs Important?
- **Debugging**: Logs help identify issues and errors in Jenkins, jobs, and build pipelines.
- **Performance Monitoring**: Track the health and performance of Jenkins nodes and jobs.
- **Security**: Access logs provide a record of user activities for auditing purposes.
- **Audit and Compliance**: Logs offer a record of actions taken on the system, useful for audits.
  
## 📝 Types of Log Files in Jenkins

### 1. 🖥️ System Logs
- **Location**: `Manage Jenkins > System Log`
- **Description**: These logs track the Jenkins server activities, including configuration changes, system events, background processes, and server startups or shutdowns.
- **Log file path**: These logs are generally stored in Jenkins' `jenkins.log` or can be found in `/var/log/jenkins/jenkins.log` (location varies depending on the installation).
- **Use Case**: Monitor Jenkins server health and investigate any issues with Jenkins configuration or startup failures.

### 2. 🛠️ Build Logs
- **Location**: Accessible from the Jenkins job or stored under the job workspace.
- **Description**: Build logs record the output of job executions. These logs contain all the steps executed during a build, such as compiling code, running tests, and deploying applications.
- **Log file path**: Each build’s log is stored under the job directory: `JENKINS_HOME/jobs/<job_name>/builds/<build_number>/log`.
- **Use Case**: Useful for analyzing job execution results, debugging failed builds, and understanding job-specific errors.

### 3. ⚙️ Node Logs
- **Location**: `Manage Jenkins > Nodes`
- **Description**: Node logs capture information related to the execution of jobs on Jenkins agent nodes (slave nodes). They log agent-related errors, connection status, and job execution details.
- **Log file path**: Typically stored in the agent workspace or available via the Jenkins UI.
- **Use Case**: Used to troubleshoot agent node connection problems, offline issues, or node-specific job failures.

### 4. 🧩 Plugin Logs
- **Location**: Varies depending on the plugin.
- **Description**: Jenkins plugins often generate their own log files, especially if they perform long-running or complex operations. Each plugin can create logs that track its own activities and any errors it encounters.
- **Log file path**: Can be found under `JENKINS_HOME/logs/<plugin_name>/` or managed through the plugin-specific configuration.
- **Use Case**: Plugin logs are essential for debugging issues related to specific Jenkins plugins, such as Git, Maven, or Pipeline plugins.

### 5. 🔐 Access Logs
- **Location**: Typically located in `JENKINS_HOME/logs/`.
- **Description**: Access logs track user interactions with the Jenkins web interface. They contain records of all HTTP requests, including user login attempts and actions performed on jobs or configurations.
- **Log file path**: Stored in `JENKINS_HOME/logs/jenkins.access.log`.
- **Use Case**: Useful for auditing user activities and investigating unauthorized access attempts or misconfigurations.

## 📂 How to Access Jenkins Logs

1. **Through the Jenkins UI**:
   - Navigate to `Manage Jenkins > System Log` for real-time log output.
   - Job-specific logs are available within each job under `Build History`.

2. **From the File System**:
   - Access the log files directly from the file system by navigating to `JENKINS_HOME/logs/` (default location).
   - Use an SSH terminal to access logs in `/var/log/jenkins/` on Linux or `C:\Program Files\Jenkins\logs\` on Windows.

3. **Via Jenkins CLI**:
   - Use Jenkins CLI commands like `jenkins-cli get-log` to fetch system logs programmatically.

## 📊 Best Practices for Managing Logs
- **Log Rotation**: Set up log rotation to prevent logs from consuming excessive disk space. This can be configured in Jenkins settings or through the operating system's log rotation services.
- **Monitor Log Size**: Regularly monitor log file sizes and archive older logs to ensure efficient disk usage.
- **Error Monitoring**: Set up alerts for critical errors found in Jenkins logs using monitoring tools like **ELK Stack** or **Splunk** to analyze log data.
- **Separate Logs by Importance**: Organize logs by importance and maintain separate logs for system events, job builds, and user access.

## ✅ Conclusion
Jenkins generates various logs that are crucial for understanding the state and performance of your CI/CD pipeline. By accessing and managing system logs, build logs, node logs, and plugin logs, you can ensure that Jenkins runs smoothly and efficiently. Regularly reviewing logs will help you quickly identify issues and resolve them before they impact your workflow.

## 📞 Contact Information
For any queries or further information, feel free to contact:

| 📛 Name       | ✉️ Email Address                    |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |


## 📚 References
- [Jenkins Log Management](https://www.jenkins.io/doc/book/managing/system-log/)
- [Jenkins CLI Documentation](https://www.jenkins.io/doc/book/managing/cli/)
- [How to Set Up Log Rotation](https://www.jenkins.io/doc/book/system-administration/monitoring/#log-rotation)

