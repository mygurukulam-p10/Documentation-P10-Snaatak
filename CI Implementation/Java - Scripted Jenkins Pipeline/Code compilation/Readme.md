# ☕ Java Code Compilation with Scripted Jenkins Pipeline

| ✍️ Author      | 📅 Created on  | 📌 Version  | 📝 Last updated by | 📅 Last edited on  |
|----------------|----------------|------------|--------------------|--------------------|
| Vinay Bansal   | 03-10-2024     | Version 1  | Vinay Bansal       | 09-10-2024         |

---

## 📚 Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙ Pre-requisites](#-pre-requisites)
3. [🔍 System Requirements](#-system-requirements)
4. [🛠️ Steps to Configure Scripted Pipelines for Code Compilation](#-steps-to-configure-scripted-pipelines-for-code-compilation)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---

## 💥 Introduction
This document provides steps to configure a **Scripted Jenkins Pipeline** for Java code compilation. Scripted Pipelines, written in Groovy, offer more flexibility compared to Declarative Pipelines, enabling the creation of complex workflows.

---

## ⚙ Pre-requisites
1. **Jenkins**: A Jenkins instance must be running.
2. **Java**: Required for Java application builds.
3. **Maven**: A build management tool for Java projects.

---

## 🔍 System Requirements
| 🖥️ Hardware Specifications | ⚙️ Minimum Requirement |
|----------------------------|------------------------|
| **Processor**               | Dual-core CPU          |
| **Memory**                  | 2 GB RAM               |
| **Disk Space**              | 10 GB                  |
| **Operating System**        | Ubuntu 22.04 LTS       |

---

## 🛠️ Steps to Configure Scripted Pipelines for Code Compilation

### 1. 🚀 **Open Jenkins Dashboard**
1. Go to the Jenkins dashboard.
2. Click on **New Item**.
3. Name the job (e.g., `code-compilation-scripted`).

### 2. 🚀 **Select Pipeline**
1. Choose **Pipeline** as the job type and click **OK**.
2. In the "Pipeline" section, switch to "Pipeline script" and enter your scripted pipeline.

### 3. 🚀 **Pipeline Script for Java Code Compilation**

Here’s an example of a **Scripted Pipeline** for Java code compilation using Maven. This pipeline includes testing stages.

```groovy
node {
    stage('Checkout') {
        // Clone the repository
        git url: 'https://github.com/your-repo/your-java-project.git'
    }

    stage('Set Up Maven') {
        // Install and set up Maven (assumes Maven is already installed in Jenkins)
        echo 'Setting up Maven environment...'
        tool name: 'Maven 3.6.3', type: 'maven'
    }

    stage('Build') {
        try {
            // Compile the Java code using Maven
            echo 'Starting build...'
            sh 'mvn clean compile'
        } catch (Exception e) {
            error 'Build failed!'
        }
    }

    stage('Run Unit Tests') {
        try {
            // Run the unit tests using Maven
            echo 'Running tests...'
            sh 'mvn test'
        } catch (Exception e) {
            error 'Tests failed!'
        }
    }

    stage('Package') {
        try {
            // Package the Java application using Maven
            echo 'Packaging application...'
            sh 'mvn package'
        } catch (Exception e) {
            error 'Packaging failed!'
        }
    }

    stage('Archive Artifacts') {
        // Archive the generated .jar or .war files
        echo 'Archiving build artifacts...'
        archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
    }

    stage('Post-Build Cleanup') {
        // Clean up after the build process
        echo 'Cleaning up workspace...'
        cleanWs()
    }
}

Explanation of the Stages:
Checkout: Clones your repository from a Git source.
Set Up Maven: Configures Maven for the build.
Build: Compiles the Java code.
Run Unit Tests: Runs unit tests to ensure the code is functional.
Package: Packages the compiled code into a JAR or WAR file.
Archive Artifacts: Archives the generated build artifacts.
Post-Build Cleanup: Cleans the workspace to avoid conflicts with future builds.
4. 🚀 Configure SCM
In the "Pipeline" section, configure the SCM settings with your Git repository URL and Jenkins credentials.

5. 🚀 Run the Build
Click Build Now to start the pipeline. You can monitor the build status and review the output in the Console.

6. 🚀 Console Output
After the build is complete, check the console output for logs and any issues encountered during the pipeline execution.

📛 Conclusion
By following this guide, you've successfully created a Scripted Jenkins Pipeline for Java code compilation. Regular builds and testing using Maven ensures continuous integration, allowing early detection of issues. Integrate this scripted pipeline into your CI/CD workflow for optimal performance.



📚 References
🔗 Links	📄 Descriptions
Build a Java app with Maven	Jenkins Tutorial on Maven Builds
Apache Maven Documentation	Official Apache Maven Documentation

