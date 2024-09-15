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
| RAM                     | 2 GB                   |
| Disk                    | 5 GB free space        |
| OS                      | Windows 10, macOS 10.14, Ubuntu 18.04 or later |

### Dependencies

| Name    | Version | Description |
|---------|---------|-------------|
| Git     | 2.0+    | Distributed version control system |
| Browser | Latest  | Web browser for accessing GitHub |

## Architecture
```
[Local Git Repository] <---> [GitHub Remote Repository]
           ^
           |
           v
[Other Team Members' Repositories]
```

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

4. Set up local repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   # Make changes to files
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```


## Contact Information

| Name            | Email address     |
|-----------------|-------------------|
| GitHub Support  | support@github.com|

## References

| Links                     | Descriptions                     |
|---------------------------|----------------------------------|
| https://docs.github.com/  | Official GitHub documentation    |
| https://git-scm.com/doc   | Git documentation                |
