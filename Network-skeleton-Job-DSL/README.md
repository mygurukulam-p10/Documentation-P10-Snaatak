# Jenkins Job DSL for Terraform Pipeline 📘

---

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------|
| Komal       | 30-10-24   | Version 1 | Komal Jaiswal   | 30-10-24       |                |                |                |

---

## Table of Contents 📑

1. [Overview](#overview)
2. [Pipeline Script](#pipeline-script)
3. [Pipeline Structure](#pipeline-structure)
4. [Setup Steps](#setup-steps)
5. [Advantages & Disadvantages ✅❌](#advantages-disadvantages)
6. [References 📚](#references)
7. [Contact Information 📞](#contact-information)

---

### 1. Overview <a name="overview"></a>

This document outlines the setup of a Jenkins pipeline for managing Terraform infrastructure. The pipeline allows users to apply or destroy infrastructure resources based on input parameters. The pipeline is designed to facilitate the deployment of infrastructure as code (IaC) using Terraform, with stages for initialization, validation, and user approval.

---

### 2. Pipeline Script <a name="pipeline-script"></a>

Here’s the Jenkins pipeline script:

```groovy
pipeline {
    agent any

    parameters {
        choice(name: 'ACTION', choices: ['apply', 'destroy'], description: 'Choose whether to apply or destroy the infrastructure')
    }

    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = 'us-east-2'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'Komal_Terraform_Network_Skeleton_Static',
                    url: 'https://github.com/mygurukulam-p10/infrastructure-repo.git',
                    credentialsId: 'git-token'
            }
        }
        stage('Setup') {
            steps {
                sh 'cd dev/Network && pwd && ls -R'
            }
        }
        stage('Terraform Init') {
            steps {
                dir('dev/Network') {
                    sh 'terraform init'
                }
            }
        }
        stage('Terraform Fmt Check') {
            steps {
                dir('dev/Network') {
                    sh 'terraform fmt'
                }
            }
        }
        stage('Terraform Validate') {
            steps {
                dir('dev/Network') {
                    sh 'terraform validate'
                }
            }
        }
        stage('Terraform Plan') {
            steps {
                dir('dev/Network') {
                    sh 'terraform plan -out=tfplan'
                }
            }
        }
        stage('Approval') {
            when {
                expression { params.ACTION == 'apply' }
            }
            steps {
                input message: 'Are you sure you want to apply the changes?', ok: 'Apply'
            }
        }
        stage('Terraform Apply or Destroy') {
            steps {
                script {
                    if (params.ACTION == 'apply') {
                        dir('dev/Network') {
                            sh 'terraform apply -auto-approve tfplan'
                        }
                    } else if (params.ACTION == 'destroy') {
                        input message: 'Are you sure you want to destroy the infrastructure?', ok: 'Destroy'
                        dir('dev/Network') {
                            sh 'terraform destroy -auto-approve'
                        }
                    }
                }
            }
        }
    }
    post {
        always {
            cleanWs()
            echo 'Cleanup completed!'
        }
        success {
            echo 'The Pipeline completed successfully!'
        }
        failure {
            echo 'The Pipeline failed :('
        }
    }
}
```

---

### 3. Pipeline Structure 📂 <a name="pipeline-structure"></a>

The Jenkins pipeline consists of the following stages:

1. **Checkout**: Clones the specified branch from the repository.
2. **Setup**: Prepares the environment and verifies the directory structure.
3. **Terraform Init**: Initializes Terraform in the specified directory.
4. **Terraform Fmt Check**: Checks the Terraform configuration for formatting issues.
5. **Terraform Validate**: Validates the Terraform configuration.
6. **Terraform Plan**: Creates an execution plan for Terraform.
7. **Approval**: Requests user approval for applying changes.
8. **Terraform Apply or Destroy**: Applies or destroys the infrastructure based on user input.
9. **Post Actions**: Cleans up the workspace and logs the result.

---

### 4. Setup Steps <a name="setup-steps"></a>

Follow these steps to create the Jenkins job:

1. 🖥️ **Go to your Jenkins Dashboard.**  
   ![Jenkins Dashboard](image-url)

2. 🖥️ **Click New Item → Enter a job name, such as Terraform-Pipeline.**  
   ![New Item](image-url)

3. 🖥️ **Provide a detailed description of the pipeline's purpose and tasks.**  
   ![Job Description](image-url)

4. 🖥️ **Create a repository to add the Jenkinsfile that will contain the pipeline script.**  
   ![Repository Setup](image-url)

5. 🖥️ **Choose Pipeline as the job type → Add your pipeline script for unit testing under the Pipeline section → Provide the repository link, credentials, and file path.**  
   ![Pipeline Configuration](image-url)

6. 🖥️ **Click on Build to initiate the pipeline.**  
   ![Start Build](image-url)

7. 🖥️ **Observe as the build completes.**  
   ![Build Progress](image-url)

8. 🖥️ **Review the Console Output for build details.**  
   ![Console Output](image-url)

9. 🖥️ **Check each stage in the console output for successful completion.**  
   ![Stage Review](image-url)

---

### 5. Advantages & Disadvantages ✅❌ <a name="advantages-disadvantages"></a>

| Advantages 😊                                          | Disadvantages 😕                                |
|------------------------------------------------------|-------------------------------------------------|
| **Infrastructure as Code**: Manages infrastructure using code | **Manual Input**: Requires user interaction for applying or destroying infrastructure |
| **Version Control**: Changes tracked in a Git repository | **Complexity**: Requires knowledge of Jenkins and Terraform |
| **Reusable**: The pipeline can be reused across different projects | **Dependency**: Relies on the correct configuration of Jenkins and Terraform |

---

### 6. References 📚 <a name="references"></a>

| Reference                      | Link                                                   |
|--------------------------------|--------------------------------------------------------|
| Jenkins Pipeline Documentation  | [Jenkins Pipelines](https://www.jenkins.io/doc/book/pipeline/) |
| Terraform Documentation        | [Terraform Docs](https://www.terraform.io/docs/index.html) |
| GitHub Repository              | [Infrastructure Repo](https://github.com/mygurukulam-p10/infrastructure-repo.git) |
| Jenkins Pipeline               | [Jenkins Pipelines](https://github.com/mygurukulam-p10/jenkins-pipelines/blob/main/Network-skeleton/JobDSL/Jenkinsfile) |

---

### 7. Contact Information 📞 <a name="contact-information"></a>

| Name          | Email address                                    |
|---------------|--------------------------------------------------|
| Komal Jaiswal | [komal.jaiswal.snaatak@mygurukulam.co](mailto:komal.jaiswal.snaatak@mygurukulam.co) |
