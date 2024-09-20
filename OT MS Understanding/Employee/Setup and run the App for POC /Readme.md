# Employee Application POC

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 05-09-24    | version 1  | Megha Tyagi     | 05-09-24       |

## Purpose
The Employee REST API is a Golang-based microservice that handles all employee-related transactions within the OT-Microservices. It is fully platform-independent and can be run on any platform. 

## Table of Contents
1. [Architecture](#architecture)
2. [Pre-requisites](#pre-requisites)
3. [System Requirements](#system-requirements)
4. [Dependencies](#dependencies)
   * [Run Time Dependencies](#run-time-dependency)
   * [Build Dependencies](#build-dependency)
5. [Important Ports](#important-ports)
6. [Repo clone](#clone-the-git-repository-with-command) 
7. [Step-by-step installation](#step-by-step-installation)
8. [Application Build](#application-build)


## Architecture


![Employee_API Architecture drawio](https://github.com/user-attachments/assets/baecdfb0-8c23-4c02-8803-d0bfee23a8e1)

## Pre-requisites
This application requires no prerequisites except for database connectivity. Additionally, Redis can be added as a caching system.

## System Requirements
| Hardware Specifications | Minimum Recommendation  |
|--------------------------|------------------------|
| Processor                | dual-core              |
| RAM                      | 4GB                    |
| Disk                     | 20GB                   |
| OS                       | Ubuntu(24.04)          |

## Dependencies
### Run time Dependency
| Name           | Version | Description                                                                                                                         |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| ScyllaDB       | 6.1.1   |ScyllaDB is a NoSQL database being utilized as the primary database in the employee application                                      |
| Redis          | 6.0.16  |Redis is an in-memory data structure store used for caching to enhance the performance and response time of the employee application.|


## Build Dependency
| Name           | Version    | Description        |
| -------------- | ---------- | ------------------ |
| Migrate        |  4.17.1    | These represent the data migration scripts or processes that ensure the data in ScyllaDB is up to date.Migrations are usually used when the database schema or structure changes.   |
| Jq       | 1.6   | jq is likely being used to parse or manipulate JSON data related to the migration process. This could involve extracting configuration values, database connection strings, or other parameters that are stored in a JSON format.| 

## Important Ports
| Inbound Traffic | Description        |
| --------------- | ------------------ |
| 6379            | Used by Redis      |
| 9042            | Used by ScyllaDB   |

## Install git

```
sudo apt install git
```


### Clone the git repository with command 



```
git clone https://github.com/OT-MICROSERVICES/employee-api.git
```


##  Step-by-step installation

### 1. Below Commands to setup scylla db

#### Install a repo file and add the ScyllaDB APT repository to your system.

  ```
  sudo mkdir -p /etc/apt/keyrings
```
  
  ```
  sudo gpg --homedir /tmp --no-default-keyring --keyring /etc/apt/keyrings/scylladb.gpg --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 491c93b9de7496a7
```
  
  ```
  sudo wget -O /etc/apt/sources.list.d/scylla.list http://downloads.scylladb.com/deb/debian/scylla-6.1.list
```


<img width="909" alt="ScyllaDB Installation" src="https://github.com/user-attachments/assets/4ce1011c-036d-4c1e-bb7b-035204bd0aad">


#### Install ScyllaDB packages.

  ```
  sudo apt-get update
```
  
  ```
  sudo apt-get install -y Scylla
```

<img width="663" alt="ScyllaDB Package" src="https://github.com/user-attachments/assets/6d74d418-355e-444a-9668-40e6ec768000">


#### Now Run the scylla_setup script to tune the system settings and determine the optimal configuration.

  ```
  sudo scylla_setup
```

<img width="743" alt="ScyllaDB SETUP" src="https://github.com/user-attachments/assets/87535646-6bda-449a-bafd-83898ec58e0f">


#### Run ScyllaDB as a service (if not already running).

 ```
 sudo systemctl start scylla-server
```
    

     Run "cqlsh" to check if it connects.

<img width="714" alt="ScyllaDB SETUP Successfully" src="https://github.com/user-attachments/assets/55093fe0-faba-4cb2-a47c-0975b389173e">


#### then create database named employee_db using below command under cqlsh

CREATE KEYSPACE employee_db 
   WITH REPLICATION = {
   'class' : 'SimpleStrategy', 
   'replication_factor' : 1 
   };


### check if db is created using command "describe keyspaces;"

### make below changes in **/etc/scylla/scylla.yaml **and add below lines at the top of the file

      authenticator: PasswordAuthenticator
      authorizer: CassandraAuthorizer

<img width="780" alt="scylla yaml file changes" src="https://github.com/user-attachments/assets/eaadcef5-0bf5-497a-8a23-4a5081884634">


#### Restart scylla-server with below command


```
sudo systemctl restart scylla-server
```


#### Firstly switch to by default super user of scylla with below command


```
cqlsh -u cassandra -p cassandra;
```


#### Now create a user in cqlsh with below command, 


```
CREATE USER scylla WITH PASSWORD 'password';
```


#### Give all permissions on keyspace employee_db to the scylla user with below command


```
GRANT ALL PERMISSIONS ON KEYSPACE employee_db TO scylla;
```


### 2.  Now need to install java 11 with below commands
   

```
sudo apt-get update
```


```
sudo apt-get install -y openjdk-11-jre-headless
```


```
sudo update-java-alternatives --jre-headless -s java-1.11.0-openjdk-amd64
```

<img width="675" alt="JDK Installation" src="https://github.com/user-attachments/assets/f5ff6df0-e108-45a7-b90d-07587b878fb7">



### 3. Install redis on the server using below commands


```
sudo apt update
```

```
sudo apt install -y redis-server
```

<img width="915" alt="Redis-Installation" src="https://github.com/user-attachments/assets/90b1667b-7e7f-46c5-bb37-6a37f745019f">

<img width="766" alt="Redis-Version" src="https://github.com/user-attachments/assets/72d14d25-4f0b-4c83-91d1-c057596e5e45">


#### Make some changes to redis conf file  "/etc/redis/redis.conf"


Look for "supervised no" and replace it with "supervised systemd"


Also replace "# requirepass foobared" with "requirepass password"

<img width="592" alt="Redis conf" src="https://github.com/user-attachments/assets/6457cf79-e91a-46da-9579-77e95c9ff081">



#### Restart redis service with below command


```
sudo systemctl restart redis.service
```


#### Now Login to redis with below command


```
redis-cli
```

<img width="365" alt="redis setup successfully" src="https://github.com/user-attachments/assets/5e0c5e0a-c9c6-42d4-b376-a9cc28c9599e">



#### Now use below command to get access of the default user in redis


```
AUTH password
```
(Here password should be same as we defined in requirepass field in redis conf file)

<img width="370" alt="image" src="https://github.com/user-attachments/assets/bee2a9e5-d314-420c-b946-fa85b1f66932">

#### Now set a scylla user with all permissions using below command


```
ACL SETUSER scylla on >password ~* +@all
```

<img width="370" alt="image" src="https://github.com/user-attachments/assets/5e190a9d-644a-4fd2-bb5e-54d4820ef4c3">


## Run time Dependency

1. #### Golang need to install for this application because Employee REST API is a golang based microservice
   
```
sudo apt install golang-go
```

<img width="352" alt="go version" src="https://github.com/user-attachments/assets/54f93d22-fbf6-491b-bcb5-0b254b5fb1cd">


2.  #### Migrate installation:V4.17.1
   
  export GOPATH=$HOME/go
  export PATH=$PATH:$GOPATH/bin
  source ~/.bashrc
  go install github.com/golang-migrate/migrate/v4@v4.17.1


<img width="923" alt="migrate installation" src="https://github.com/user-attachments/assets/84f3b907-e08d-4da3-b80c-c34aac801aff">

<img width="398" alt="migrate installed successfully" src="https://github.com/user-attachments/assets/05c1bc74-d51f-4a5a-a188-d2ac53c6e1e9">


3. #### Install jq Makefile and any associated scripts or configurations
   
```
sudo apt-get install jq -y
```
```
jq --version
```

<img width="613" alt="jq installed" src="https://github.com/user-attachments/assets/e88eab96-a1ad-4b51-9122-3fa97a94c105">


## Application Build

  #### Run the following command inside the directory to build your software artifact.
  #### Run the command, For building the application, we can use make command. 

 ```
 make build
```

 <img width="414" alt="Makebuild run successfully" src="https://github.com/user-attachments/assets/0e18fda8-8eaf-4b33-8e88-ddf15886acac">


#### For execution of the unit test cases, code coverage reports, etc:

   go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
   #For HTML report visualization
   go tool cover -html=cover.out


<img width="858" alt="test cases, code coverage reports run successfully" src="https://github.com/user-attachments/assets/7acd4fd8-0228-4047-9575-4917d3aca660">


#### To automate the process of applying database migrations in a project, use below mentioned command

```
make run-migrations
```


#### Once the keyspace and table is initialized, we can run the application by this command 

export GIN_MODE=release
 #For debugging set gin mode to development
./employee-api


<img width="910" alt="Run application Successfully" src="https://github.com/user-attachments/assets/b98ce091-c8ec-418b-9a79-d4a6dea08d77">



#### For dev testing, the Swagger UI can be used for sample payload generation and requests. The swagger page will be accessible on

http://localhost:8080/swagger/index.html

#### Here is the dashboard comes when you hit this above mentioned link

<img width="920" alt="Employee-api deshboard" src="https://github.com/user-attachments/assets/aac263d6-6598-49d9-9f3b-f5ffa5e3a3e7">


#### For healthcheck,click on health check api to check application health and outcomes looks like below mentioned dashboard image

<img width="782" alt="application health check" src="https://github.com/user-attachments/assets/336f569f-ba13-4a4a-aa58-a79390a54988">
