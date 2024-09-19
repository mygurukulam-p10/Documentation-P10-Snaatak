![image](https://github.com/user-attachments/assets/11ed2c89-d5d3-4714-abdd-90f74195a6f9)

# Redis - Setup and POC ( Standalone Redis )

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal Jaiswal  | 10-09-24    | Version 1  | Komal Jaiswal      | 19-09-24       |

## Table of Contents
1. [Purpose](#1-purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
   - [Important Ports](#important-ports)
3. [Installation and Setup](#3-installation-and-setup)
   - [3.1 Installation](#31-installation)
   - [3.2 Configuration](#32-configuration)
   - [3.3 Redis Configuration and Authentication Steps](#33-Redis-configuration-and-authentication-steps)
   - [3.4 Starting Redis](#34-starting-redis)
4. [Conclusion](#4-conclusion)
5. [References](#5-references)

## 1. Purpose

The purpose of the Redis in API's is to store the cache data so that, next time it doesn't need to ask database again and again to fetch it and create a time latency.

## 2.  Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | 2 cores                |
| RAM                     | 4GB                    |
| Disk                    | 15GB SSD               |
| OS                      | Ubuntu 22.04 LTS       |

### Dependencies

#### Run time Dependency

| Name    | Version | Description                                    |
|---------|---------|------------------------------------------------|
| Redis   |  6.0.16 | Redis is an in-memory data structure store used for caching to enhance the performance and response time of the attendance application. |

### Important Ports

| Inbound Traffic | Description                    |
|-----------------|--------------------------------|
| 6379            | Default Port Redis             |

![image](https://github.com/user-attachments/assets/32d559fd-20f3-4895-8e5a-c93156849e58)

## 3. Installation and Setup

### 3.1 Installation

Redis can be installed on various operating systems. Follow the steps below for your specific OS:

#### Ubuntu/Debian

To install Redis on Ubuntu or Debian-based systems:
```
sudo apt update
sudo apt install redis-server
```
![image](https://github.com/user-attachments/assets/e7f0f4a7-3da0-41c4-8a93-d6d27068258b)

#### CentOS/RHEL
```
sudo yum install epel-release
sudo yum install redis
```

#### MacOS (using Homebrew)
```
brew install redis
```

#### Windows
```
For this we have to download a window installer for redis Redis MSI installer https://github.com/microsoftarchive/redis/releases
```

### 3.2 Configuration

### 1. Redis Setup

#### 1.1 Installation
Follow the [Redis installation guide](https://redis.io/download) for your platform (Linux, macOS, or Windows).

#### 1.2 Configuration

#### Locate the Redis Configuration File:
- **Linux:** `/etc/redis/redis.conf`
- **MacOS:** `/usr/local/etc/redis.conf`
- **Windows:** `C:\Program Files\Redis\redis.windows.conf`

#### Edit the Configuration File: 
**Note :-** Further in this documentation we will be using Linux Ubuntu.

```
sudo nano /etc/redis/redis.conf
```
![image](https://github.com/user-attachments/assets/c2feae73-a9f0-4c7e-bf41-b3a728a30f1c)

#### Apply Configuration Changes

Update the Redis configuration file with the following settings:

| Configuration           | Description                                                              |
|-------------------------|--------------------------------------------------------------------------|
| `bind 127.0.0.1 ::1`     | Restricts Redis to listen only on the localhost IPv4 and IPv6 addresses. |
| `protected-mode yes`     | Enables Redis's security feature to prevent unauthorized access by default. |
| `port 6379`              | Specifies that Redis should listen for incoming connections on port 6379.  |


![image](https://github.com/user-attachments/assets/cfa5c160-c3fb-4d6d-8a65-dd2c8569b1ed)

### 1.3 Security Setup

According to the application we are working on like Employee API , Attendance API and Salary API we will use the below command to access the default user.And How can we make that more Secure.

#### 1.3 Redis Configuration and Authentication Steps

#### 1. Edit Redis Configuration File

1. **Locate the Redis configuration file:**
   ```
   sudo nano /etc/redis/redis.conf
   ```
#### 2. Update the following lines:

- Change ```supervised no``` to ```supervised systemd```

- Uncomment and set the password by replacing ```# requirepass foobared``` with
  ```requirepass redos-101```

Save and Exit the Editor.

#### **Restart Redis**

```
sudo systemctl restart redis
```

#### 3. Authenticate with Redis

Use the redis-cli to authenticate with the password you set:

```
redis-cli
AUTH <your_password>
AUTH redos-101
```
**Note :-** redis-101 is password I have generated

#### 4. Set Up a User with All Permissions

1. Create a user with all permissions:

```
ACL SETUSER <user_name> on ><<set_password>> ~* +@all 
ACL SETUSER scylla on >redos-102 ~* +@all
```
**Note :-** I am using ```scylla``` as a ```username``` because in my application I have to access database with more security.

**Note:** The > redos-102 ( Password that is set for my redis),this part sets the user's password to redos-102.


## 4. Conclusion

Redis is a popular choice for applications that require low-latency and high-throughput data access. By following best practices in tuning and security, Redis can be a robust component of your technology stack, offering scalability and reliability for modern application needs.

### 5. References

| **Reference**                       | **Description**                                                  |
|-------------------------------------|------------------------------------------------------------------|
| [Redis Documentation](https://redis.io/documentation)        | Official Redis documentation covering features, setup, and usage. |
| [Redis Command Reference](https://redis.io/commands)         | Comprehensive guide to Redis commands and their usage.            |
| [Redis Community](https://redis.io/community)                | Community resources, forums, and discussions about Redis.         |
| [Redis Detailed Document](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Detailed%20Document/README.md) | In-depth Redis documentation and setup guide.                     |



## 6. Contact Information 
| Name | Email Address |
|:---:|:---:|
| Komal | komal.jaiswal.snaatak@mygurukulam.co |
