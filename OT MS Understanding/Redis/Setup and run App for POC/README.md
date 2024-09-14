# Redis - Setup and POC ( Standalone Redis )

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal Jaiswal  | 10-09-24    | version 1  | Komal Jaiswal      | 11-09-24       |

## Table of Contents

1. [Installation and Setup](#1-installation-and-setup)
   - [1.1 Installation](#11-installation)
   - [1.2 Configuration](#12-configuration)
   - [1.3 Security Setup](#13-security-setup)
   - [1.4 Starting Redis](#14-starting-redis)
2. [Cleanup and Shutdown](#7-cleanup-and-shutdown)
3. [Conclusion](#8-conclusion)
4. [References](#9-references)
---

## 1. Installation and Setup

### 1.1 Installation

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

### 1.2 Configuration

## 1. Redis Setup

### 1.1 Installation
Follow the [Redis installation guide](https://redis.io/download) for your platform (Linux, macOS, or Windows).

### 1.2 Configuration

#### Locate the Redis Configuration File:
- **Linux:** `/etc/redis/redis.conf`
- **MacOS:** `/usr/local/etc/redis.conf`
- **Windows:** `C:\Program Files\Redis\redis.windows.conf`

#### Edit the Configuration File:
```
sudo nano /etc/redis/redis.conf
```
![image](https://github.com/user-attachments/assets/c2feae73-a9f0-4c7e-bf41-b3a728a30f1c)

#### Apply Configuration Changes

Update the Redis configuration file with the following settings:

```
bind 127.0.0.1 ::1
protected-mode yes
port 6379
```
![image](https://github.com/user-attachments/assets/cfa5c160-c3fb-4d6d-8a65-dd2c8569b1ed)

### 1.3 Security Setup

**Set a Strong Password:**

```
requirepass your_strong_password
```

### 1.4 Starting Redis

**For Systems Using systemd:**
```
sudo systemctl start redis-server
```
**Manual Start with Configuration File:**
```
redis-server /path/to/redis.conf
```
## 7. Cleanup and Shutdown

To clean up Redis, stop the server and remove any persistent files if needed:
```
sudo systemctl stop redis-server
sudo rm /var/lib/redis/dump.rdb
sudo rm /var/lib/redis/appendonly.aof
```

## 8.Conclusion

Redis is a popular choice for applications that require low-latency and high-throughput data access. By following best practices in tuning and security, Redis can be a robust component of your technology stack, offering scalability and reliability for modern application needs.

### 9. References

| **Reference**                       | **Description**                                                  |
|-------------------------------------|------------------------------------------------------------------|
| [Redis Documentation](https://redis.io/documentation)        | Official Redis documentation covering features, setup, and usage. |
| [Redis Command Reference](https://redis.io/commands)         | Comprehensive guide to Redis commands and their usage.            |
| [Redis Community](https://redis.io/community)                | Community resources, forums, and discussions about Redis.         |
| [Redis Detailed Document](https://github.com/mygurukulam-p10/Documention/blob/main/OT%20MS%20Understanding/Redis/Detailed%20Document/README.md) | In-depth Redis documentation and setup guide.                     |



## Contact Information 
| Name | Email Address |
|:---:|:---:|
| Komal | komal.jaiswal.snaatak@mygurukulam.co |
