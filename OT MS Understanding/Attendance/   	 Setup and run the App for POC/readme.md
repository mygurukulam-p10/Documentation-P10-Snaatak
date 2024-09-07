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
5. [Repo clone](##clone-the-git-repository-with-command) 
6. [Step-by-step installation](##step-by-step-installation)
7. [Application Build](##application-build)
8. [Architecture](##architecture)

## Purpose
Attendance Microservices is designed in Python to manage Attendance information.

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | single-core              |
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
| Liquibase      |   18    | A database schema change management tool, used during application deployment or setup.|
| Poetry         |         | A dependency management and packaging tool for Python. Used during the build phase for installing Python dependencies.|
| Java           |   17    | Required for Java-based build or runtime environments.|
| Python         |  3.11   | Required for running Python applications.|
| Pip            |  3.11   | Used for installing Python packages.|


## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 6379            | Used by Redis      |
| 5234            | Used by Post gres  |

## Clone-the-git-repository-with-command

```
git clone https://github.com/OT-MICROSERVICES/attendance-api.git
```
```
## Script to install all dependencies at ones

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
java -version
python3 --version
pip3 --version

echo "All installations completed successfully!"
```
```
# Installation of Poetry


```
## Application Build


## Architecture 
![image](https://github.com/user-attachments/assets/42c73d72-2652-400f-89f3-bb78de2c8169)

