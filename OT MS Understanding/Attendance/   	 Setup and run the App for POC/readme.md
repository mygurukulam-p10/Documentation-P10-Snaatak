
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
5. [Repo clone](#clone-the-git-repository-with-command) 
6. [Step-by-step installation](#step-by-step-installation)
7. [Application Build](#application-build)
8. [Architecture](#architecture)

## Purpose
Attendance Microservices is designed in Python to manage Attendance information.

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 20GB                   |
| OS                       | Ubuntu(22.04)          |

## Dependencies

### Run time Dependency
| Name           | Version | Description                                                                                                                         |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| Postgres SQL   | 15      |Postgresis is that database being utilized as the primary database in the Attendance application.|
| Redis          | 6.0.16  |Redis is an in-memory data structure store used for caching to enhance the performance and response time of the attendance application.|

### Build Dependency

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

## Clone-the-git-repository-with-command

```
git clone https://github.com/OT-MICROSERVICES/attendance-api.git
```

## Script to install all dependencies at ones

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

![Screenshot from 2024-09-07 13-07-34](https://github.com/user-attachments/assets/a6cc56e5-ec3a-4d0b-aa66-65b7fb1bcb1e)

![Screenshot from 2024-09-07 13-07-39](https://github.com/user-attachments/assets/9280d7ae-42b3-4ba2-8cc5-96b32dfecc3b)




### Step 1 :- Run Below Command
 A library required for developing applications that interact with PostgreSQL databases. It includes header files and the static library for libpq, which is the C application programmer's interface to PostgreSQL.

```
sudo apt-get install build-essential libpq-dev
```


### Step 2 :- Update the Redis Configuration (redis.conf)
Open redis.conf configuration file (located at /etc/redis/redis.conf).
Find the line that starts with # requirepass, which is commented out by default.
Set a password by uncommenting the line and replacing your_password with your desired password:

![Screenshot from 2024-09-07 16-17-56](https://github.com/user-attachments/assets/b0c0a4ce-4e7f-4b58-8504-9565deee4d06)

### Step 3 :- Go to Attendance Repository and run command poetry shell to create virtual env 
```
poetry shell
``` 
![Screenshot from 2024-09-07 14-53-39](https://github.com/user-attachments/assets/ec6c03a5-66d0-4eea-8994-4383a87d0f61)

### Step 4:- Create database for attendance app and setup password for postgres user
```
Create database attendence_db;

```
```
ALTER USER postgres WITH PASSWORD 'password';
```

### Step 5: - Update pg_hba.conf
The pg_hba.conf file controls client authentication and is where you specify the authentication method for different users and connections.

Locate the pg_hba.conf file: The location of this file may vary depending on installation. Common locations are /etc/postgresql/15/main/pg_hba.conf
Edit the pg_hba.conf file:

![Screenshot from 2024-09-07 16-22-31](https://github.com/user-attachments/assets/771865af-7b47-4e10-b254-f595485f680e)

### Step 6: - Update config.yaml and liquibase.properties
![Screenshot from 2024-09-07 16-24-36](https://github.com/user-attachments/assets/41edd2c8-a83e-42c9-ad00-9b5bdf138e79)

![Screenshot from 2024-09-07 16-28-35](https://github.com/user-attachments/assets/7b331115-1538-42ce-989e-65a64ae7b3ea)

### Step 7 :- Run the below command to install all dependencies required in this project 
```
poetry Install
```
![Screenshot from 2024-09-07 14-53-49](https://github.com/user-attachments/assets/972d301e-68ba-4e36-bc54-ada0c6948e4e)

## Application Build

### Step 8 :- Run Make migration command 
```
make run-migrations
```
![Screenshot from 2024-09-07 14-54-22](https://github.com/user-attachments/assets/14e582b3-ef33-4db1-9433-88525720aa45)


### Step 9 :- Firstly install gunicorn and Now Run the Application
```
pip3 install gunicorn
```
```
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080
```
![Screenshot from 2024-09-07 14-54-32](https://github.com/user-attachments/assets/00fd81a3-9816-4cb5-806a-2f20329493ce)


### Step 10 :- Now go to web browser and hit url http://<ip of the server>:8080/apidocs
![Screenshot from 2024-09-07 13-27-05](https://github.com/user-attachments/assets/7b109c86-527a-4336-9ae9-f0d3b46e295f)


## Architecture 
![image (1)](https://github.com/user-attachments/assets/09a7e5bf-7a95-4493-a192-3cc3e0e887d9)


