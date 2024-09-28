# SonarQube Quality Gates Documentation

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 24-09-24    | version 1  | Amit Nagar      | 25-09-24       |

## Table of Contents
1. [Introduction](#introduction)
2.  [Flow_Diagram](#Flow-diagram)
3. [What is SonarQube Quality Gate?](#what-is-sonarqube-quality-gate)
4. [Why Use Quality Gates?](#why-use-quality-gates)
5. [Types of Quality Gates](#types-of-quality-gates)
6. [Implementation of Quality Gates](#implementation-of-quality-gates)
7. [Advantages of Using Quality Gates](#advantages-of-using-quality-gates)
8. [Advantages and Disadvantages of Using Quality Gates](#Advantages-disadvantage)
9. [Conclusion](#conclusion)
10.  [Contact Information](#Contact-Information)
11. [References](#references)

## Introduction
SonarQube is an open-source platform for continuous inspection of code quality. It helps developers manage code quality and security vulnerabilities while maintaining high standards across software projects. Quality gates are a crucial feature within SonarQube that determines whether a project meets the predefined quality criteria before moving to the next phase of development.

## Flow Diagram

![image](https://github.com/user-attachments/assets/30e7662f-a53e-4f7a-9809-8d9cf5696523)

## What is SonarQube Quality Gate?
A Quality Gate is a set of conditions that a project must meet before it can be considered satisfactory. These conditions may include metrics related to code coverage, code duplications, maintainability, reliability, security, and more. Quality gates help enforce coding standards and ensure that code changes do not degrade the quality of the existing codebase.

## Why Use Quality Gates?
- **Early Detection**: Identify issues early in the development process to reduce the cost of fixing them later.
- **Continuous Improvement**: Encourage teams to strive for higher quality code with every release.
- **Team Accountability**: Promote accountability among team members regarding code quality.
- **Automated Feedback**: Provide immediate feedback to developers about the quality of their code, allowing for quicker adjustments.

## Types of Quality Gates
SonarQube allows the creation of different types of quality gates, including:
| Type                | Description                                                  |
|---------------------|--------------------------------------------------------------|
| **Default Quality Gate** | Predefined set of conditions focused on essential metrics. |
| **Custom Quality Gate**  | User-defined gate tailored to project-specific needs.      |
| **Branch Quality Gate**  | Conditions applied to branches (e.g., feature, release).   |

# Implementation of Quality Gates

## Step 1: Set Up a SonarQube Project

1. **Log in to SonarQube**
   - Open the SonarQube dashboard by navigating to the URL where SonarQube is hosted.
   - Log in using your credentials.

![Screenshot from 2024-09-25 00-27-30](https://github.com/user-attachments/assets/8b740c5f-9958-4bda-a0c3-92ef804235ba)


2. **Create a New Project**
   - From the main dashboard, go to the **Projects** tab.
   - Click on **Create Local Project**.
 


![Screenshot from 2024-09-25 00-44-25](https://github.com/user-attachments/assets/4fb008b5-331e-40c4-a71d-66f1c452f0a7)


3. **Configure Project Key and Display Name**
   - Set the **Project Key** (a unique identifier for the project).
   - Set the **Display Name** (how it will appear on the dashboard).
   - Enter the project name (e.g., `Attendence`).
   - 
![Screenshot from 2024-09-25 00-44-43](https://github.com/user-attachments/assets/07acf260-d565-4dc4-8a5b-5e05717fe332)


![Screenshot from 2024-09-25 00-45-27](https://github.com/user-attachments/assets/2fdb529c-5ba2-4bfd-be25-f1ddd0ac697c)

![Screenshot from 2024-09-25 00-45-50](https://github.com/user-attachments/assets/e3a3acac-2c96-4d33-8332-08d8a3efb841)


4. **Generate Authentication Token**
   - After the project is created, SonarQube will prompt you to generate a **token**.
   - Click **Generate**, and copy the token to a secure location for later use.

![Screenshot from 2024-09-25 00-46-00](https://github.com/user-attachments/assets/345e374d-3289-4fe3-b7b8-3c2e8ac95a20)


5. **Configure Your Build Tool**
   - Integrate SonarQube with your build tool (e.g., Maven, Gradle, Jenkins, or GitHub Actions).
   - Use the generated token to authenticate the scans from your build tool.
  
![Screenshot from 2024-09-25 00-47-27](https://github.com/user-attachments/assets/be5bdc7c-530c-4af6-ae55-e0baefdbd93e)


![Screenshot from 2024-09-25 00-47-49](https://github.com/user-attachments/assets/b2819c82-9d35-4c7a-9705-134e7d2e86e8)


6. **Install SonarQube Scanner**
   - Install the SonarQube scanner locally
   - create a file called sonar-project.properties where we will define sonarqube properties
  
   ![Screenshot from 2024-09-25 00-56-03](https://github.com/user-attachments/assets/da4ef10e-06e8-40bd-8842-230cb26fef25)

  - cat sonarqube properties file
    ![Screenshot from 2024-09-25 00-56-32](https://github.com/user-attachments/assets/40b3a50b-87b9-495b-bb5a-025111569f6c)



7: **Run sonar scanner inside the root folder of attendence api salary**

![Screenshot from 2024-09-25 00-56-52](https://github.com/user-attachments/assets/978f69eb-1d11-4aa1-983e-22fdd584dfa5)


![Screenshot from 2024-09-25 00-57-00](https://github.com/user-attachments/assets/5577df0c-e035-4fac-9626-140d78672481)

8: **Analysis report on sonarqube of attendence api**

![Screenshot from 2024-09-25 00-57-22](https://github.com/user-attachments/assets/028166bd-3f78-4ca4-ab92-a9aaea18e6d4)

![Screenshot from 2024-09-25 00-57-44](https://github.com/user-attachments/assets/08b045dc-2b31-4baf-9fb3-bc261e0e7f48)


# Advantages and Disadvantages of Using Quality Gates

| Advantages                        | Disadvantages                   |
|-----------------------------------|---------------------------------|
| **Improved Code Quality**         | **Increased Development Time**  |
| Ensures adherence to coding standards. | May slow down the development process. |
| **Early Detection of Issues**     | **Resistance from Developers**  |
| Identifies issues before they escalate. | Some may view them as obstacles. |
| **Consistent Delivery**           | **Overhead of Maintenance**     |
| Promotes uniformity in code delivery. | Requires continuous effort to manage. |
| **Increased Transparency**        | **Potential for False Positives** |
| Provides visibility into project health. | Tools may flag non-critical issues. |
| **Higher Customer Satisfaction**  | **False Sense of Security**     |
| Leads to fewer bugs and better user experience. | Meeting criteria doesn’t ensure a bug-free product. |


## Conclusion
SonarQube Quality Gates play a vital role in maintaining code quality throughout the software development lifecycle. By implementing Quality Gates, organizations can ensure that their projects meet specific quality criteria, leading to more maintainable, reliable, and secure software products.


## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

## References

| Reference                                      | Link                                                 |
|------------------------------------------------|------------------------------------------------------|
| SonarQube Documentation                          | [SonarQube Documentation](https://docs.sonarqube.org/latest/) |
| SonarQube Quality Gates Overview                 | [Quality Gates Overview](https://docs.sonarqube.org/latest/analysis/scan/sonarqube-quality-gates/) |
| Effective Use of SonarQube for Code Quality Management | [SonarQube Official Site](https://sonarqube.org/) |


