# PostgreSQL Database POC


|  Author        | Created on |  Version  | Last updated by  | Last edited on |
|----------------|------------|-----------|------------------|----------------|
| Abhinav Singh  |   07-09-24 | version 1 |   Abhinav Singh  |     08-09-24   |

## Table of Contents
1. [Introduction](#introduction)
2. [Architecture](#architecture)
3. [Pre-requisites](#pre-requisites)
4. [System Requirements](#system-requirements)
5. [Dependencies](#dependencies)
6. [Important Ports](#important-ports)
7. [Step-by-step installation](#step-by-step-installation)
8. [Postgres UI](#postgres-ui)
9. [Postgres Basic Operations](#postgres-basic-operations)
## Introduction
PostgreSQL is an open-source, advanced relational database management system known for its extensibility and standards compliance. It supports both SQL querying and features like JSON storage, making it versatile for modern applications.

It was created to provide a powerful, reliable, and scalable database solution that addresses the need for an open-source, enterprise-grade system capable of handling complex data requirements.

## Architecture
![image](https://github.com/user-attachments/assets/6847ab70-b4b3-4546-be08-981937551cc3)

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

Installing PostgreSQL on Ubuntu via apt automatically resolves dependencies of PostgreSQL.

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
postgresql-contrib is a package of additional features, like extensions and modules, that enhance PostgreSQL's functionality.
```
sudo apt install postgresql postgresql-contrib -y
```
![image](https://github.com/user-attachments/assets/d1a0851f-e54a-4a7e-99d1-5b2ca224e4de)
It will install the latest version of postgres.

### To install a specific version of Postgres we can specify version
```
sudo apt install postgresql-<version> postgresql-contrib-<version> -y
```
### Verify that PostgreSQL is running
```
sudo systemctl status postgresql
```
![image](https://github.com/user-attachments/assets/002c8516-966c-4955-baa8-c64359205967)

### If not running then Start the PostgreSQL service and ensure it runs at startup
```
sudo systemctl start postgresql
sudo systemctl enable postgresql
```
![image](https://github.com/user-attachments/assets/1e23a3e4-232f-40a7-b8ff-6aba3332817f)


### PostgreSQL creates a user named postgres by default. Switch to this user to interact with PostgreSQL

```
sudo -i -u postgres
```
### Once logged in as postgres user, you can access the PostgreSQL shell with below command

```
psql
```
![image](https://github.com/user-attachments/assets/a9eeaed3-a795-4e40-bac4-1e4f5df7827a)

## Postgres UI
PostgreSQL does not have it's own User Interface but PostgreSQL offers several User Interface (UI) tools that provide a graphical way to interact with your PostgreSQL databases.

One of the most popular UI tool for PostgreSQL that I am covering in this document is pgAdmin.

pgAdmin is the most popular open-source administration and development platform for PostgreSQL.

**To download pgAdmin on local ubuntu machine with GUI we can use below commands -**

**Update apt repository**
```
sudo apt update
```
![image](https://github.com/user-attachments/assets/d01a21bc-8612-4333-9868-fd3fa0fcf530)

**Install the public key for the repository (if not done previously)**
```
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```
![image](https://github.com/user-attachments/assets/14512a60-119d-44bc-9cfb-6fab70fdb0ae)

**Create the repository configuration file**
```
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```
![image](https://github.com/user-attachments/assets/6dff3551-0186-4461-91ae-7cbbe711e3b6)

**Install pgAdmin for desktop**
```
sudo apt install pgadmin4-desktop
```
![image](https://github.com/user-attachments/assets/8b3f295e-654e-493d-ad0b-b9c5aa56a5a4)

**Now navigate to search bar and search for pgAdmin**

![image](https://github.com/user-attachments/assets/efbd2da1-d6e7-4881-a732-394d359317e5)


**Allow Access to PostgreSQL on EC2 Instance**

By default, PostgreSQL only listens on localhost. We need to configure it to listen on all interfaces or a specific IP, so it can accept remote connections.

**To do so Edit the PostgreSQL configuration file (postgresql.conf)**
```
sudo vi /etc/postgresql/16/main/postgresql.conf
```
Locate to listen_addresses and change 'localhost' with '*' ,also uncomment the line

You can also specify any particular IP address if want,
![image](https://github.com/user-attachments/assets/e4842f08-1610-49f8-a2a4-4fad587979e0)

**Also edit the pg_hba.conf file which controls client authentication**
```
sudo vi /etc/postgresql/16/main/pg_hba.conf
```
allow connections from all IPs by replacing <127.0.0.1/32> with 0.0.0.0/0
![image](https://github.com/user-attachments/assets/88447011-cf5d-48b1-a483-b4c1ed55b95b)

**Restart PostgreSQL service to apply changes made to postgresql.conf file**
```
sudo systemctl restart postgresql
```
**set password for default postgres user**

Login to postgres user using sudo with below command
```
sudo -i -u postgres
```
Navigate to postgresql shell with below command
```
psql
```
Change password for user with below command
```
ALTER USER postgres PASSWORD 'new_password';
```
![image](https://github.com/user-attachments/assets/9cdd4bc3-0d37-4fd3-a0ba-f4eb23960270)


**Now Openup pgAdmin desktop and look for Object in upper left corner and choose Register and then select server**\

We will get a tab for general settings where we can provide a naming identity to our server.
![image](https://github.com/user-attachments/assets/824106ed-e3bc-41e9-9228-b8fbf4ec754b)

Then we will move to the connection settings and will specify hostname, username and password for our postgres server and select save option.
![image](https://github.com/user-attachments/assets/ab381447-2585-4a8c-98a5-b2e92baa6ae6)

Now we can see our Postgres server in left navigation bar under servers.
![image](https://github.com/user-attachments/assets/de70087b-a8c5-4ef3-ab39-13053c9504f4)


## Basic Operations in PostgreSQL

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
![image](https://github.com/user-attachments/assets/a0f5f198-bfbd-49e9-a6a9-0922c86abf31)

### To create a table inside the created database mydb
```
CREATE TABLE mytable (ID SERIAL PRIMARY KEY,name VARCHAR(100),type VARCHAR(50));
```
![image](https://github.com/user-attachments/assets/5a48d1bf-2f82-4b60-8f27-8faada6410cb)

### To insert values in the created table mytable
```
INSERT INTO mytable (ID, name, type) 
VALUES (1, 'John Doe', 'Employee');
```
![image](https://github.com/user-attachments/assets/5822360b-4e9c-4dd0-83ed-d0cd58bb7c7f)

### To fetch all values from table created
```
select * from mytable
```
![image](https://github.com/user-attachments/assets/a072e2de-05d0-4c15-83c2-5cdda75a24eb)

