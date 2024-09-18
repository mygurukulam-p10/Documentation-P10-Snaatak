# GitHub Version Control System (VCS) Setup: Proof of Concept

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 15-09-24    | version 1  | Amit Nagar      | 16-09-24       |

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
3. [Architecture](#architecture)
4. [Step-by-step installation of GitHub](#step-by-step-installation-of-github)
5. [Conclusion](#Conclusion)
6. [Contact Information](#contact-information)


## Purpose
This Poc demonstrates how to set up and use GitHub as a Version Control System. GitHub provides a centralized platform for collaborative software development, offering features like version control, issue tracking, and project management.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| RAM                     | 1 GB                   |
| Disk                    | 8 GB free space        |
| OS                      | Windows 10, macOS 10.14, Ubuntu 18.04 or later |

### Dependencies

| Name    | Version | Description |
|---------|---------|-------------|
| Git     | 2.34    | Distributed version control system |


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
   touch index.html
   git add index.html
   git commit -m "added index.html"
   git push origin main
   ```
   ![Screenshot from 2024-09-15 13-34-17](https://github.com/user-attachments/assets/83d1acfc-e6d6-4b23-8185-8ea195a3e1a6)

   ![Screenshot from 2024-09-17 00-04-07](https://github.com/user-attachments/assets/07238f92-318e-4533-afb5-118b38e3cc11)

   ![Screenshot from 2024-09-17 00-04-27](https://github.com/user-attachments/assets/bae063c7-0fc2-4dfb-84fc-447ec203533f)

   ![Screenshot from 2024-09-17 00-04-49](https://github.com/user-attachments/assets/11f7093f-ea52-4495-bd70-de8e12b35279)



## Conclusion

In this Proof of Concept (PoC), we demonstrated the basic process of creating a repository, cloning it, and pushing changes. This workflow allows developers to track modifications, collaborate smoothly, and ensure an organized approach to managing project files and updates. By following these steps, teams can streamline their development efforts and enhance productivity across the board.

## Contact Information

| Name            | Email address     |
|-----------------|-------------------|
| Amit Nagar      | amit.nagar.snaatak@mygurukulam.com|


