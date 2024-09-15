# GitHub Version Control System (VCS) Setup: Proof of Concept

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
3. [Architecture](#architecture)
4. [Step-by-step installation of GitHub](#step-by-step-installation-of-github)
5. [Contact Information](#contact-information)
6. [References](#references)

## Purpose
This PoC demonstrates how to set up and use GitHub as a Version Control System. GitHub provides a centralized platform for collaborative software development, offering features like version control, issue tracking, and project management.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| RAM                     | 1 GB                   |
| Disk                    | 5 GB free space        |
| OS                      | Windows 10, macOS 10.14, Ubuntu 18.04 or later |

### Dependencies

| Name    | Version | Description |
|---------|---------|-------------|
| Git     | 2.34    | Distributed version control system |
| Browser | Latest  | Web browser for accessing GitHub |

## Architecture
![Screenshot from 2024-09-15 13-27-09](https://github.com/user-attachments/assets/e5b133a5-9045-49a9-8023-b9ebd9102f88)



## Step-by-step installation of GitHub

1. Install Git:
   ```bash
   # Windows (using Chocolatey)
   choco install git

   # macOS (using Homebrew)
   brew install git

   # Ubuntu
   sudo apt-get update
   sudo apt-get install git
   ```

2. Create a GitHub account at [github.com](https://github.com)

3. Create a new repository on GitHub:
   - Click the "+" icon in the top-right corner
   - Select "New repository"
   - Name your repository
   - Click "Create repository"

![Screenshot from 2024-09-15 13-33-08](https://github.com/user-attachments/assets/b0f63f44-21ce-4fe8-aa1e-6205af926d0b)

![Screenshot from 2024-09-15 13-34-08](https://github.com/user-attachments/assets/1c1eed9d-ca0c-4f25-af18-9ef947a74f7b)


4. Set up local repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   # Make changes to files
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```
   ![Screenshot from 2024-09-15 13-34-17](https://github.com/user-attachments/assets/83d1acfc-e6d6-4b23-8185-8ea195a3e1a6)

   ![Screenshot from 2024-09-15 13-35-07](https://github.com/user-attachments/assets/d460b58c-b9c3-46a6-a55b-e08a659a3884)

   ![Screenshot from 2024-09-15 13-35-25](https://github.com/user-attachments/assets/fb04b7a2-e7ad-42cd-93aa-2711a602c0e5)

   ![Screenshot from 2024-09-15 13-43-50](https://github.com/user-attachments/assets/297f92d9-4bf9-494d-8ee2-118c029190a4)



## Contact Information

| Name            | Email address     |
|-----------------|-------------------|
| Amit Nagar      | amit.nagar.snaatak@mygurukulam.com|

## References

| Links                     | Descriptions                     |
|---------------------------|----------------------------------|
| https://docs.github.com/  | Official GitHub documentation    |
| https://git-scm.com/doc   | Git documentation                |
