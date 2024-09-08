# PostgreSQL Database POC


|  Author  | Created on |  Version  | Last updated by | Last edited on |
|----------|------------|-----------|-----------------|----------------|
| Abhinav  |   9-08-24  | version 1 |     Abhinav     |     9-08-24    |


## Table of Contents
1. [Pre-requisites](#pre-requisites)
2. [System Requirements](#system-requirements)
3. [Dependencies](#dependencies)
4. [Important Ports](#important-ports)
5. [Step-by-step installation](#step-by-step-installation)
6. [Architecture](#architecture)

## Purpose
PostgreSQL was created to provide a powerful, reliable, and scalable database solution that addresses the need for an open-source, enterprise-grade system capable of handling complex data requirements.

## Pre-requisites
This application requires no prerequisites except for remote connection to the server to install PostgreSQL on.

## System Requirements

| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 20GB                   |
| OS                       | Ubuntu(22.04)          |

## Dependencies

Installing PostgreSQL on Ubuntu via apt automatically resolves dependencies.

## Important Ports
| Inbound Traffic |   Description      |
| --------------- | ------------------ |
|      5432       |  Used by Postgres  |


# Step-by-step installation

## Update the package list and upgrade existing packages-with-command

```
sudo apt update && sudo apt upgrade -y
```
![image](https://github.com/user-attachments/assets/665c8501-5136-454e-b1bf-791a2d7230d3)

## Install PostgreSQL along with postgresql-contrib, which adds useful tools for database management.

```
sudo apt install postgresql postgresql-contrib -y
```
![image](https://github.com/user-attachments/assets/d1a0851f-e54a-4a7e-99d1-5b2ca224e4de)

### Start the PostgreSQL service and ensure it runs at startup

```
sudo systemctl start postgresql
sudo systemctl enable postgresql
```
![image](https://github.com/user-attachments/assets/1e23a3e4-232f-40a7-b8ff-6aba3332817f)

### Verify that PostgreSQL is running

```
sudo systemctl status postgresql
```
![image](https://github.com/user-attachments/assets/002c8516-966c-4955-baa8-c64359205967)

### PostgreSQL creates a user named postgres by default. Switch to this user to interact with PostgreSQL

```
sudo -i -u postgres
```
### Once logged in as postgres user, you can access the PostgreSQL shell with below command

```
psql
```
![image](https://github.com/user-attachments/assets/a9eeaed3-a795-4e40-bac4-1e4f5df7827a)

## Inside the PostgreSQL shell, you can create a new database user and a new database

### To create a new user use command

```
CREATE USER myuser WITH PASSWORD 'mypassword';
```
![image](https://github.com/user-attachments/assets/e2da016d-ed83-4279-84a0-fc5750b4965d)

### To create a new database
 
```
CREATE DATABASE mydb OWNER myuser;
```
![image](https://github.com/user-attachments/assets/9a6153f6-dab4-4cec-9176-3dc62d2d4f0a)

### To Grant all privileges on the database to the user-
```
GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```
![image](https://github.com/user-attachments/assets/af95f3ea-608c-487c-95e3-4b8e2d290a85)

### You can now test the connection to the new PostgreSQL database
```
psql -U myuser -d mydb -h 127.0.0.1 -W
```
