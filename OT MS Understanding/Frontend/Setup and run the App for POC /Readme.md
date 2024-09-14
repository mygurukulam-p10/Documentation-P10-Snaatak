# Employee Application POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 12-09-24    | version 1  | Megha Tyagi     | 14-09-24       |

## Purpose
The purpose of this POC is to demonstrate the functionality and integration of the ReactJS-based frontend application as the main UI for the OT-Microservices stack. This POC will validate the application's cross-platform compatibility, confirm its ability to operate with only JavaScript runtime modules, and verify the seamless execution of web page operations using the ReactJS framework. Additionally, the POC aims to test the integration and reliability of test cases for ensuring proper application functionality.

## Table of Contents
1. [Architecture](#architecture)
2. [System Requirements](#system-requirements)
3. [Dependencies](#dependencies)
   * [Build Dependencies](#build-dependency)
4. [Step-by-step installation](#step-by-step-installation)

## Architecture


## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 20GB                   |
| OS                       | Ubuntu(22.04)          |

## Dependencies
### Build Dependency
| Name           | Version    | Description        |
| -------------- | ---------- | ------------------ |
| Npm      |  6.14.18   | To manage and install the necessary third-party packages that the ReactJS application relies on. |
|Node      | v14.21.3  | Node.js is critical for the build and development of your ReactJS frontend, as it powers the package management, build processes, and local development server necessary for the project.|

                                                                      
## Steps-By-Steps Installation

#### Step 1:- Clone-the-git-repository-with-command
```
git clone https://github.com/OT-MICROSERVICES/frontend.git
```
#### Step 2:- Install all dependencies for API

**Below Command Adds the NodeSource Node.js 14.x repository to the system's package list, ensuring you can install or upgrade to Node.js 14 using your package manager (apt).**
```
sudo add-apt-repository "deb https://deb.nodesource.com/node_14.x $(lsb_release -sc) main"
```
<img width="920" alt="Screenshot 2024-09-14 115134" src="https://github.com/user-attachments/assets/23b95490-eeec-47e0-aa42-fcc432a6e296">

**The command installs Node.js on your system using the APT package manager.**
```
sudo apt install nodejs 
```
<img width="959" alt="npm install" src="https://github.com/user-attachments/assets/a3eb0f6d-ebf3-4343-9d67-24c8538b57bf">

**The command downloads and runs the NVM (Node Version Manager) installation script**
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash
   # Load nvm into your shell session
   export NVM_DIR="$HOME/.nvm"
   [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
    # Optionally, you can also load nvm automatically by adding the following to your ~/.bashrc or ~/.zshrc:
   # export NVM_DIR="$HOME/.nvm"
   # [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```
<img width="956" alt="image" src="https://github.com/user-attachments/assets/95fd63cb-f18f-4c11-aaa2-a69b34185d6b">

**The index.html file in a React project serves as the template for the single-page application. It contains a div with the id="root", where the entire React app is rendered, and links static assets like icons and manifests for production builds.**
- firstly we need to create a directory called "**public**"
  and add file "**index.html**"

**Run the command, For building the application, we can use make command.**
```
makebuild
```
![Screenshot 2024-09-10 124307](https://github.com/user-attachments/assets/977bab9f-b6f3-487c-a3cd-f3103bf85c73)

**Now below installs the Serve package globally using npm, which is a simple static file server for hosting local websites.**
```
npm install -g serve
```
<img width="912" alt="image" src="https://github.com/user-attachments/assets/5ef4e6f6-2824-4977-8bd8-e3091cf53cea">

**Below command serves a production build of a React application from the build directory using the Serve package, creating a local server to host the static files.**

```
serve -s build
```
<img width="926" alt="image" src="https://github.com/user-attachments/assets/b3dacbcc-3836-4d76-af7f-af6500c2b90a">

Then hit the url which is showing in above terminal ss "http://10.0.0.4:3000" replace the IP with correct one and get the Buildpiper dashboard

![Screenshot 2024-09-10 125259](https://github.com/user-attachments/assets/d0f5fb09-cd3c-4297-bcfb-6ddc7fa09ea0)

![Screenshot 2024-09-10 170624](https://github.com/user-attachments/assets/78c32c6a-44a0-4328-86cb-2bcb72b9d089)



 

