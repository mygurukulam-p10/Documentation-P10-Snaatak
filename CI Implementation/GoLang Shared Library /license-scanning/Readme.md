# License Scanning for Shared Library 
---  

| ✍ Author      | 📅 Created on  | 📌 Version    | 📝 Last updated by | 📅 Last edited on  | Reviewer L0 | Reviewer L1 | Reviewer L2 |
|---------------|----------------|--------------|--------------------|-------------------|-------------|-------------|-------------|
| Amit Nagar    | 20-10-2024      | Version 1    | Amit Nagar         | 20-10-2024        |             |             |             |
---
## Table of Contents
1. [💥 Introduction](#-introduction)
2. [⚙️ Pre-requisites](#-pre-requisites)
3. [🚀 Global Configurations](#-global-configurations)
4. [💥 Steps to Configuration for License Scanning](#-steps-to-configuration-for-license-scanning)
5. [📛 Conclusion](#-conclusion)
6. [📧 Contact Information](#-contact-information)
7. [📚 References](#-references)

---
### 💥 Introduction
License scanning is crucial for identifying the licenses of third-party libraries utilized by this shared library. By integrating license scanning into the CI/CD pipeline, we ensure compliance with licensing requirements, mitigating legal risks.

---

## ⚙️ Pre-requisites

| Dependency      | Version   | Description                                                     |
|-----------------|-----------|-----------------------------------------------------------------|
| **Jenkins**      | Latest    | A continuous integration server to run the Trivy scans.       |
| **Trivy**        | Latest    | A tool for scanning container images and checking for vulnerabilities and licenses. |
| **Git**          | Latest    | Required for version control and fetching project dependencies. |


---
# 💥 Steps to Configure License Scanning in Jenkins

### 1. 🚀 **Open Jenkins Dashboard**
   - Access your Jenkins server through your browser and log in to your dashboard.

### 2. 🚀 **Create a New Job**
   - Click on **New Item** in the Jenkins dashboard.
   - **Enter a name** for your job, for example, `License Scanning`.
   - Choose **Pipeline** as the job type and click **OK**.

### 3. 🚀 **Provide a Job Description**
   - In the **Description** section, write a brief description of what this pipeline does, such as "This pipeline performs license scanning to ensure all dependencies are compliant."

### 4. 🚀 **Create a Repository and Add Vars File**
   - Set up a repository that contains a `vars` file. This file will store configurations or reusable functions to be used within your pipeline script.
   - Ensure that the repository is accessible and integrated with Jenkins.

### 5. 🚀 **Configure Pipeline Script**
 
   ![Pipeline Configuration](https://github.com/user-attachments/assets/321766a3-b5c8-4b42-971c-bc479e12bde1)

### 6. 🚀 **Run the Pipeline**
   - Click on **Build Now** to trigger the pipeline.

### 7. 🚀 **Check the Build Status**
   - Once the pipeline is complete, you will see the status of the build in the Jenkins dashboard.
   
   ![Build Complete Screenshot](https://github.com/user-attachments/assets/283f74ff-8049-4c11-90e1-2fc5b5b4da6f)
   ![Build Success Screenshot](https://github.com/user-attachments/assets/287c6516-2861-4235-9d23-ad0bdd362587)

### 8. 🚀 **View Console Output**
   - Click on **Console Output** in the left-hand menu to view the detailed logs of the build process, including any issues or successes related to the License Scanning.

   ![Console Output Screenshot 1](https://github.com/user-attachments/assets/1fb0d806-1fe4-4aae-b174-0f9abffd456e)
   ![Console Output Screenshot 2](https://github.com/user-attachments/assets/10372db5-7d79-4612-a374-bafb2588662d)
   
### 9. 🚀 **Set Up Email Notifications**
![Screenshot from 2024-10-21 18-31-35](https://github.com/user-attachments/assets/f1f77a2e-e55c-4a55-9a47-ebe814e3470b)


Jenkinsfile
```
@Library('shared1') _  // Load the shared library

pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from')
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL')
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository')
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
        string(name: 'OUTPUT_REPORT_FILE', defaultValue: 'trivy-license-report.json', description: 'Trivy output report file name')
    }

    stages {
        stage('Checkout Code') {
            steps {
                script {
                    // Directly call the gitCheckout function
                    gitCheckout(params.BRANCH_NAME, params.CREDENTIALS_ID, params.REPO_URL)
                }
            }
        }

        stage('Download and Install Trivy') {
            steps {
                script {
                    // Directly call the installTrivy function
                    installTrivy('0.51.4')
                }
            }
        }

        stage('Run Trivy License Scan') {
            steps {
                script {
                    // Directly call the runLicenseScan function
                    runLicenseScan(params.OUTPUT_REPORT_FILE)
                }
            }
        }

        stage('Archive Trivy Report') {
            steps {
                script {
                    // Directly call the archiveReport function
                    archiveReport(params.OUTPUT_REPORT_FILE)
                }
            }
        }
    }

    post {
        success {
            script {
                String successSubject = "Trivy License Scan Successful - Build #${env.BUILD_NUMBER}"
                String successBody = """
                The Trivy License Scan has completed successfully.

                Details:
                - Branch: ${params.BRANCH_NAME}
                - Repository: ${params.REPO_URL}
                - Build Number: ${env.BUILD_NUMBER}

                Please find the attached Trivy License Report.
                """
                email(successSubject, successBody, params.REPORT_RECIPIENT, params.OUTPUT_REPORT_FILE)
            }
        }
        failure {
            script {
                String failureSubject = "Trivy License Scan Failed - Build #${env.BUILD_NUMBER}"
                String failureBody = """
                The Trivy License Scan has failed.

                Details:
                - Branch: ${params.BRANCH_NAME}
                - Repository: ${params.REPO_URL}
                - Build Number: ${env.BUILD_NUMBER}

                Please check the logs for more details.
                """
                email(failureSubject, failureBody, params.REPORT_RECIPIENT, params.OUTPUT_REPORT_FILE)
            }
        }
        always {
            script {
                echo "Pipeline execution finished."
            }
        }
    }
}


```

installTrivy.groovy

```
def call(version) {
    // Check if Trivy is installed, and only install if not present
    if (sh(script: 'command -v trivy', returnStatus: true) != 0) {
        echo "Trivy not found, installing version ${version}..."
        sh """
        wget https://github.com/aquasecurity/trivy/releases/download/v${version}/trivy_${version}_Linux-64bit.deb
        sudo dpkg -i trivy_${version}_Linux-64bit.deb
        """
    } else {
        echo "Trivy is already installed, skipping installation."
    }
}

```
email.groovy

```
def call(String subject, String body, String recipient, String attachmentsPattern = '') {
    emailext(
        subject: subject,
        body: body,
        to: recipient,
        attachmentsPattern: attachmentsPattern
    )
}


```
archiveReport.groovy
```
def call(reportFile) {
    archiveArtifacts artifacts: reportFile, allowEmptyArchive: true
}

```
runLicenseScan.groovy
```
def call(String outputFile = 'trivy-license-report.json') {
    sh "trivy repo --scanners license --format json --output ${outputFile} ."
}
```

[GoLang Shared Library Jenkinsfile](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/GoLang-Shared-Library/license-scaning/Jenkinsfile)
[GoLang Shared Library Repository](https://github.com/mygurukulam-p10/jenkins-shared-library)

---

## 📛 Conclusion
Integrating license scanning into our Jenkins pipeline is a crucial step in ensuring that our shared library complies with licensing requirements for third-party dependencies. This automated approach not only enhances legal compliance but also enables early detection of potential licensing issues during development.

---
## 📞 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |


---

## 📚 References

| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| https://spdx.dev/                                 | **SPDX - Software Package Data Exchange** |
| https://opensource.org/licenses                   | **Open Source Licenses** |
| https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/License-Scanning-POC|**Manual POC**|
