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
| **Jenkins**      | Latest    | A continuous integration server to run the FOSSA scans.       |
| **FOSSA**        | Latest    | A tool for scanning code and managing open-source licenses.    |
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

### 4. 🚀 **Configure Pipeline Script**


### 5. 🚀 **Run the Pipeline**
   - Click on **Build Now** to trigger the pipeline.

### 6. 🚀 **Check the Build Status**
   - Once the pipeline is complete, you will see the status of the build in the Jenkins dashboard.
  

### 7. 🚀 **View Console Output**
   - Click on **Console Output** in the left-hand menu to view the detailed logs of the build process, including any issues or successes related to the License Scanning.


### 8. 🚀 **Email Notifications**


### Jenkinsfile
```groovy
@Library('shared1') _  // Load the shared library

pipeline {
    agent any

    parameters {
        string(name: 'BRANCH_NAME', defaultValue: 'main', description: 'Branch to build from')
        string(name: 'REPO_URL', defaultValue: 'git@github.com:mygurukulam-p10/employee-api.git', description: 'Git repository URL')
        string(name: 'CREDENTIALS_ID', defaultValue: 'amit_cred', description: 'Credentials ID for accessing the repository')
        string(name: 'REPORT_RECIPIENT', defaultValue: 'nagar.amit1999@gmail.com', description: 'Email address to send the build report')
        string(name: 'OUTPUT_REPORT_FILE', defaultValue: 'fossa-license-report.json', description: 'FOSSA output report file name')
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

        stage('Run FOSSA License Scan') {
            steps {
                script {
                    // Directly call the runLicenseScan function
                    runLicenseScan(params.OUTPUT_REPORT_FILE)
                }
            }
        }

        stage('Archive FOSSA Report') {
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
                String successSubject = "FOSSA License Scan Successful - Build #${env.BUILD_NUMBER}"
                String successBody = """
                The FOSSA License Scan has completed successfully.

                Details:
                - Branch: ${params.BRANCH_NAME}
                - Repository: ${params.REPO_URL}
                - Build Number: ${env.BUILD_NUMBER}

                Please find the attached FOSSA License Report.
                """
                email(successSubject, successBody, params.REPORT_RECIPIENT, params.OUTPUT_REPORT_FILE)
            }
        }
        failure {
            script {
                String failureSubject = "FOSSA License Scan Failed - Build #${env.BUILD_NUMBER}"
                String failureBody = """
                The FOSSA License Scan has failed.

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

## 📞 Contact Information

| Name       | Email address                     |
|------------|-----------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

---

## 📚 References

| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| [SPDX - Software Package Data Exchange](https://spdx.dev/) | **SPDX - Software Package Data Exchange** |
| [Open Source Licenses](https://opensource.org/licenses)                   | **Open Source Licenses** |
| [Manual POC](https://github.com/mygurukulam-p10/Documentation-P10-Snaatak/tree/main/Application%20CI%20Design/License-Scanning-POC)|**Manual POC**|
