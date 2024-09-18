
# ATTENDANCE API POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 06-09-24    | version 1  | Amit Nagar      | 17-09-24       |

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
3. [System Requirements](#system-requirements)
4. [Dependencies](#dependencies)
   * [Run Time Dependencies](#run-time-dependency)
   * [Build Dependencies](#build-dependency)
5. [Important Ports](#important-ports)
6. [Architecture](#architecture)
7. [Step-by-step installation](#step-by-step-installation)
8. [Application Build](#application-build)
9. [Contact Information](#contact-information)



## Purpose
We are preparing this document so that we can easily install **Attendance Microservices** which is designed in Python to manage Attendance information.

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | single-core              |
| RAM                      | 1GB                    |
| Disk                     | 10GB                   |
| OS                       | Ubuntu(22.04)          |

## Dependencies

### Run time Dependency
| Name           | Version | Description                                                                                                                         |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| Postgres SQL   | 15      |Postgresis is that database being utilized as the primary database in the Attendance application.|
| Redis          | 6.0.16  |Redis is an in-memory data structure store used for caching to enhance the performance and response time of the attendance application.|

## Build Dependency

| Name           | Version | Description                                                                                                                      |
| -------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Liquibase      | 4.29.2  | A database schema change management tool, used during application deployment or setup.|
| Poetry         | 1.8.3   | A dependency management and packaging tool for Python. Used during the build phase for installing Python dependencies.|
| Java           | 17.0.12 | Required for Java-based build or runtime environments.|
| Python         | 3.11    | Required for running Python applications.|
| Pip            | 3.11    | Used for installing Python packages.|


## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 6379            | Used by Redis      |
| 5432            | Used by Postgres  |



## Architecture

![image](https://github.com/user-attachments/assets/45c3aa9e-06b6-4ea2-bc72-e275bf5738cf)


# Step-by-step installation

## Step 1:- Clone-the-git-repository-with-command

```
git clone https://github.com/OT-MICROSERVICES/attendance-api.git
```

## Step 2:- Script to install all dependencies at ones

Create a script file with any name like dependency.sh and paste below script inside it and give permission of execution to it

```
#!/bin/bash

# Update package list and upgrade existing packages
sudo apt update && sudo apt upgrade -y

# Install PostgreSQL 15
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt update
sudo apt install -y postgresql-15 postgresql-contrib-15
sudo systemctl enable postgresql
sudo systemctl start postgresql

# Install Redis (latest version from default repositories)
sudo apt install -y redis-server
sudo systemctl enable redis-server
sudo systemctl start redis-server

# Install Liquibase
wget -O- https://repo.liquibase.com/liquibase.asc | gpg --dearmor > liquibase-keyring.gpg
cat liquibase-keyring.gpg | sudo tee /usr/share/keyrings/liquibase-keyring.gpg > /dev/null
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/liquibase-keyring.gpg] https://repo.liquibase.com stable main' | sudo tee /etc/apt/sources.list.d/liquibase.list
sudo apt update
sudo apt install -y liquibase

# Install Java 17
sudo apt install -y openjdk-17-jdk
sudo update-alternatives --set java /usr/lib/jvm/java-17-openjdk-amd64/bin/java

# Install Python 3.11
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update
sudo apt install -y python3.11 python3.11-venv python3.11-dev
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.11 1
sudo update-alternatives --set python3 /usr/bin/python3.11

# Install Poetry
curl -sSL https://install.python-poetry.org | python3 -
export PATH="$HOME/.local/bin:$PATH"
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc

# Install pip for Python 3.11
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.11 get-pip.py
rm get-pip.py

# Verify installations
echo "Verifying installations..."
psql --version
redis-server --version
liquibase --version
poetry --version
java -version
python3 --version
pip3 --version

echo "All installations completed successfully!"
```
![Screenshot from 2024-09-16 16-39-14](https://github.com/user-attachments/assets/2a05a0ed-1391-4215-9a63-4b8d98382404)

![Screenshot from 2024-09-16 16-39-41](https://github.com/user-attachments/assets/223964f4-8d5e-466f-a3ac-ce2b426660f2)

![Screenshot from 2024-09-17 09-59-10](https://github.com/user-attachments/assets/e1d1757b-99b2-4701-ba01-fe761ee3f7a8)


![Screenshot from 2024-09-16 23-27-33](https://github.com/user-attachments/assets/1934f2b3-e9c2-4811-81e0-be98b9a9bf39)

![Screenshot from 2024-09-17 09-43-33](https://github.com/user-attachments/assets/7cfc4e62-9df6-4a5e-ac0c-1c8fb9598f0e)


### Step 3 :- Run Below Command
 A library required for developing applications that interact with PostgreSQL databases. It includes header files and the static library for libpq, which is the C application programmer's interface to PostgreSQL.

```
sudo apt-get install build-essential libpq-dev
```

### Step 4:- Create database for attendance app and setup password for postgres user

First, switch to the postgres user with sudo su postgres. Then, access the PostgreSQL prompt by typing psql and press Enter. No password is needed at this point. This starts the PostgreSQL interactive terminal where you can run SQL commands.

![Screenshot from 2024-09-18 18-03-54](https://github.com/user-attachments/assets/20fb94a3-ef92-4a88-be4a-e1c5a8ada56a)


```
Create database attendence_db;

```
![Screenshot from 2024-09-18 18-06-29](https://github.com/user-attachments/assets/8e1a4173-9a62-4d32-95c7-d0fbc9486cbc)

```
ALTER USER postgres WITH PASSWORD 'arsenal1234';
```

![Screenshot from 2024-09-18 18-07-50](https://github.com/user-attachments/assets/dc4980d5-c97f-4196-a052-4bf76663fdb7)

### Step 5: - Update pg_hba.conf
The pg_hba.conf file controls client authentication and is where you specify the authentication method for different users and connections.

Locate the pg_hba.conf file: The location of this file may vary depending on installation. Common locations are /etc/postgresql/15/main/pg_hba.conf
Edit the pg_hba.conf file:

Change the authentication method for the postgres user from peer to md5. This will require the postgres user to authenticate using a password hashed with the MD5 method, rather than the peer method which uses the operating system user for authentication.

![Screenshot from 2024-09-16 16-41-41](https://github.com/user-attachments/assets/238c9e35-fd61-403a-8c7a-afef0cc0b842)


### Step 6 :- Go to Attendance Repository and run command poetry shell to create virtual env 

![Screenshot from 2024-09-17 20-24-43](https://github.com/user-attachments/assets/24486a8a-f2f1-4554-8c2e-9c1008bb140a)

```
cd /home/ubuntu/attendance-api
```

![Screenshot from 2024-09-17 20-25-03](https://github.com/user-attachments/assets/17a74e4e-293e-424f-9993-09ca301643d0)


```
poetry shell
```

![Screenshot from 2024-09-16 23-28-06](https://github.com/user-attachments/assets/cf51617e-f466-4543-9f95-ea1dfeb1530e)


### Step 7: - Update config.yaml and liquibase.properties

![Screenshot from 2024-09-17 20-25-03](https://github.com/user-attachments/assets/61caaea2-e821-4610-8325-d746922bca8f)

Ensure that config.yaml includes details for both PostgreSQL and Redis, as this file will be used to connect our application with postgres and redis.

![Screenshot from 2024-09-18 18-18-35](https://github.com/user-attachments/assets/30ea69a4-3d50-4d0c-8655-33fc35da0ac9)




The liquibase.properties file is used to configure Liquibase, a database schema change management tool, allowing us to manage version-controlled database changes.

![Screenshot from 2024-09-18 18-20-03](https://github.com/user-attachments/assets/c67d4e3d-de80-40bb-ba45-4b66678081ab)



### Step 8 :- Run the below command to install all dependencies required in this project 
```
poetry Install
```
![Screenshot from 2024-09-16 23-49-40](https://github.com/user-attachments/assets/fa81fe48-84cb-4708-9121-41f712ca2c27)


## Application Build

### Step 9 :- Run Make migration command 
```
make run-migrations
```
![Screenshot from 2024-09-17 09-49-42](https://github.com/user-attachments/assets/78e37536-8b24-4844-9091-547dc49be5bf)


### Step 10 :- Firstly install gunicorn and Now Run the Application
```
pip3 install gunicorn
```
```
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080
```
![Screenshot from 2024-09-16 23-28-59](https://github.com/user-attachments/assets/7b3e25c2-c2ad-444b-8ec0-9155a449a356)

For more details of Gunicorn [here](https://github.com/mygurukulam-p10/Documention/tree/main/VCS%20Design%20%2B%20POC/Gunicorn/Introduction)

### Step 11 :- Now go to web browser and hit url http://<IP_OF_SERVER>:8080/apidocs

![Screenshot from 2024-09-07 13-27-05](https://github.com/user-attachments/assets/a9bcb393-bd64-46a2-a908-5ec34283937a)


## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

