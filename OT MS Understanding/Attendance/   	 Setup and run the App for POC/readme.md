
# ATTENDANCE API POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 06-09-24    | version 1  | Amit Nagar      | 06-09-24       |

## Table of Contents
1. [Pre-requisites](#pre-requisites)
2. [System Requirements](#system-requirements)
3. [Dependencies](#dependencies)
   * [Run Time Dependencies](#run-time-dependency)
   * [Build Dependencies](#build-dependency)
4. [Important Ports](#important-ports)
5. [Step-by-step installation](#step-by-step-installation)
6. [Application Build](#application-build)


## Purpose
We are preparing this document so that you can easily install **Attendance Microservices** which is designed in Python to manage Attendance information.

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | sinle-core              |
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
| Migrate        | 4.17.1  | These represent the data migration scripts or processes that ensure the data in ScyllaDB is up to date.
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

# Install Migrate
curl -L https://packagecloud.io/golang-migrate/migrate/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/migrate-keyring.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/migrate-keyring.gpg] https://packagecloud.io/golang-migrate/migrate/ubuntu/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/migrate.list
sudo apt update
sudo apt install -y migrate

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
migrate -version
liquibase --version
poetry --version
java -version
python3 --version
pip3 --version

echo "All installations completed successfully!"
```
![Screenshot from 2024-09-13 09-30-17](https://github.com/user-attachments/assets/8f17900b-9123-43fe-a313-5f570ad30e2e)

![Screenshot from 2024-09-13 09-30-55](https://github.com/user-attachments/assets/b583487a-ff33-4e44-a7df-42ca23b9dcdc)

![Screenshot from 2024-09-13 09-31-12](https://github.com/user-attachments/assets/e564b676-740b-48cf-bb7a-1675d69198bb)

![Screenshot from 2024-09-13 09-31-24](https://github.com/user-attachments/assets/06b1d378-e4ea-4166-b23f-d22db54d4b91)

![Screenshot from 2024-09-13 09-31-35](https://github.com/user-attachments/assets/bd798cb7-86b8-4d4a-a914-155ee9aa3df0)

![Screenshot from 2024-09-13 09-31-44](https://github.com/user-attachments/assets/f2001b67-47d4-462c-84af-54bb67c0449e)

### Step 3 :- Run Below Command
 A library required for developing applications that interact with PostgreSQL databases. It includes header files and the static library for libpq, which is the C application programmer's interface to PostgreSQL.

```
sudo apt-get install build-essential libpq-dev
```


### Step 4 :- Update the Redis Configuration (redis.conf)
Open redis.conf configuration file (located at /etc/redis/redis.conf).
Find the line that starts with # requirepass, which is commented out by default.
Set a password by uncommenting the line and replacing your_password with your desired password:

![Screenshot from 2024-09-07 16-17-56](https://github.com/user-attachments/assets/b0c0a4ce-4e7f-4b58-8504-9565deee4d06)

### Step 5 :- Go to Attendance Repository and run command poetry shell to create virtual env 
```
poetry shell
``` 
![Screenshot from 2024-09-07 14-53-39](https://github.com/user-attachments/assets/ec6c03a5-66d0-4eea-8994-4383a87d0f61)

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

![Screenshot from 2024-09-07 16-22-31](https://github.com/user-attachments/assets/771865af-7b47-4e10-b254-f595485f680e)

### Step 8: - Update config.yaml and liquibase.properties
![Screenshot from 2024-09-07 16-24-36](https://github.com/user-attachments/assets/41edd2c8-a83e-42c9-ad00-9b5bdf138e79)

![Screenshot from 2024-09-07 16-28-35](https://github.com/user-attachments/assets/7b331115-1538-42ce-989e-65a64ae7b3ea)

### Step 9 :- Run the below command to install all dependencies required in this project 
```
poetry Install
```
![Screenshot from 2024-09-07 14-53-49](https://github.com/user-attachments/assets/972d301e-68ba-4e36-bc54-ada0c6948e4e)

## Application Build

### Step 10 :- Run Make migration command 
```
make run-migrations
```
![Screenshot from 2024-09-07 14-54-22](https://github.com/user-attachments/assets/14e582b3-ef33-4db1-9433-88525720aa45)


### Step 11 :- Firstly install gunicorn and Now Run the Application
```
pip3 install gunicorn
```
```
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080
```
![Screenshot from 2024-09-07 14-54-32](https://github.com/user-attachments/assets/00fd81a3-9816-4cb5-806a-2f20329493ce)


### Step 12 :- Now go to web browser and hit url http://<IP_OF_SERVER>:8080/apidocs

![Screenshot from 2024-09-07 13-27-05](https://github.com/user-attachments/assets/7b109c86-527a-4336-9ae9-f0d3b46e295f)


## Conclusion

The Attendance Microservices is a Python application designed to efficiently manage attendance data. It requires a dual-core processor, 4GB RAM, and 20GB of disk space on Ubuntu 22.04. Key dependencies include PostgreSQL 15 for the database and Redis 6.0.16 for optional caching. Essential tools for setup include Migrate, Liquibase, Poetry, Java 17, Python 3.11, and Pip 3.11. After cloning the repository and running the dependency script, we need to configure PostgreSQL and Redis, install necessary tools, update configuration files, and run migrations before starting the application with Gunicorn. API documentation can be accessed via a web browser.


## Contact Information

| Name       | Email address     |
|------------|-------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com |

