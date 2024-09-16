
# ATTENDANCE API POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 06-09-24    | version 1  | Amit Nagar      | 06-09-24       |

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
9. [Conclusion](#Conclusion)
10. [Contact Information](#contact-information)



## Purpose
We are preparing this document so that you can easily install **Attendance Microservices** which is designed in Python to manage Attendance information.

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

![image](https://github.com/user-attachments/assets/35166bb1-44ed-4950-af79-4a4a32a964f9)

# Step-by-step installation

## Step 1:- Clone-the-git-repository-with-command

```
git clone https://github.com/OT-MICROSERVICES/attendance-api.git
```

## Step 2:- Script to install all dependencies at ones

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

![Screenshot from 2024-09-16 16-39-27](https://github.com/user-attachments/assets/3652397f-c52f-42c6-9c03-23ec384b651a)

![Screenshot from 2024-09-16 16-39-41](https://github.com/user-attachments/assets/223964f4-8d5e-466f-a3ac-ce2b426660f2)

![Screenshot from 2024-09-16 16-39-55](https://github.com/user-attachments/assets/c88516a5-3750-4c55-baf9-1c0c1f3bc0e7)

![Screenshot from 2024-09-16 16-40-03](https://github.com/user-attachments/assets/572d1be5-3466-40ed-bea7-2791a92f4556)

![Screenshot from 2024-09-16 16-40-38](https://github.com/user-attachments/assets/b9bae0dd-dc8c-416e-9c8b-871e78a09a0c)


### Step 3 :- Run Below Command
 A library required for developing applications that interact with PostgreSQL databases. It includes header files and the static library for libpq, which is the C application programmer's interface to PostgreSQL.

```
sudo apt-get install build-essential libpq-dev
```


### Step 4 :- Update the Redis Configuration (redis.conf)
Open redis.conf configuration file (located at /etc/redis/redis.conf).
Find the line that starts with # requirepass, which is commented out by default.
Set a password by uncommenting the line and replacing your_password with your desired password:

![Screenshot from 2024-09-16 16-41-03](https://github.com/user-attachments/assets/d5452953-ed02-46b0-b4a5-26898a160c2c)


### Step 5 :- Go to Attendance Repository and run command poetry shell to create virtual env 
```
poetry shell
``` 
![Screenshot from 2024-09-16 16-41-17](https://github.com/user-attachments/assets/06fb62c5-5ef0-45f9-b550-1e44cb5535d1)


### Step 6:- Create database for attendance app and setup password for postgres user
```
Create database attendence_db;

```
```
ALTER USER postgres WITH PASSWORD 'password';
```

### Step 7: - Update pg_hba.conf
The pg_hba.conf file controls client authentication and is where you specify the authentication method for different users and connections.

Locate the pg_hba.conf file: The location of this file may vary depending on installation. Common locations are /etc/postgresql/15/main/pg_hba.conf
Edit the pg_hba.conf file:

![Screenshot from 2024-09-16 16-41-41](https://github.com/user-attachments/assets/238c9e35-fd61-403a-8c7a-afef0cc0b842)


### Step 8: - Update config.yaml and liquibase.properties
![Screenshot from 2024-09-16 16-41-51](https://github.com/user-attachments/assets/dd6db804-5537-4080-ba73-254a4590a1c7)

![Screenshot from 2024-09-16 16-42-08](https://github.com/user-attachments/assets/3f4edb7b-52aa-44de-8aae-9971de5b74d8)



### Step 9 :- Run the below command to install all dependencies required in this project 
```
poetry Install
```
![Screenshot from 2024-09-16 16-42-17](https://github.com/user-attachments/assets/67b1f49d-d03d-4862-a442-a42361e56a0e)


## Application Build

### Step 10 :- Run Make migration command 
```
make run-migrations
```
![Screenshot from 2024-09-16 16-42-29](https://github.com/user-attachments/assets/4a815b54-014a-40d6-a356-5d9969cd07de)



### Step 11 :- Firstly install gunicorn and Now Run the Application
```
pip3 install gunicorn
```
```
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080
```
![Screenshot from 2024-09-16 16-42-39](https://github.com/user-attachments/assets/f2ec9c11-37f8-431c-8860-bb9b79389895)


### Step 12 :- Now go to web browser and hit url http://<IP_OF_SERVER>:8080/apidocs

![Screenshot from 2024-09-07 13-27-05](https://github.com/user-attachments/assets/a9bcb393-bd64-46a2-a908-5ec34283937a)


## Conclusion

The Attendance Microservices is a Python application designed to efficiently manage attendance data. It requires a dual-core processor, 4GB RAM, and 20GB of disk space on Ubuntu 22.04. Key dependencies include PostgreSQL 15 for the database and Redis 6.0.16 for optional caching. Essential tools for setup include Migrate, Liquibase, Poetry, Java 17, Python 3.11, and Pip 3.11. After cloning the repository and running the dependency script, we need to configure PostgreSQL and Redis, install necessary tools, update configuration files, and run migrations before starting the application with Gunicorn. API documentation can be accessed via a web browser.


## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

