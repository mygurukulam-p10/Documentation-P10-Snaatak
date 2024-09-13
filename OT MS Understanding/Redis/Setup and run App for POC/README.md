# Redis Proof of Concept (POC) 

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal Jaiswal  | 10-09-24    | version 1  | Komal Jaiswal      | 11-09-24       |

## Table of Contents

1. [Installation and Setup](#1-installation-and-setup)
   - [1.1 Installation](#11-installation)
   - [1.2 Configuration](#12-configuration)
   - [1.3 Security Setup](#13-security-setup)
   - [1.4 Starting Redis](#14-starting-redis)
2. [Basic Operations](#2-basic-operations)
   - [2.1 Connecting to Redis](#21-connecting-to-redis)
   - [2.2 String Operations](#22-string-operations)
   - [2.3 List Operations](#23-list-operations)
   - [2.4 Hash Operations](#24-hash-operations)
   - [2.5 Set Operations](#25-set-operations)
   - [2.6 Sorted Set Operations](#26-sorted-set-operations)
3. [Advanced Features](#3-advanced-features)
   - [3.1 Pub/Sub Messaging](#31-pubsub-messaging)
   - [3.2 Transactions](#32-transactions)
   - [3.3 Lua Scripting](#33-lua-scripting)
   - [3.4 Pipelining](#34-pipelining)
   - [3.5 Geospatial Operations](#35-geospatial-operations)
4. [Persistence Configuration](#4-persistence-configuration)
   - [4.1 RDB (Redis Database)](#41-rdb-redis-database)
   - [4.2 AOF (Append-Only File)](#42-aof-append-only-file)
5. [Monitoring and Benchmarking](#5-monitoring-and-benchmarking)
   - [5.1 Monitoring](#51-monitoring)
   - [5.2 Benchmarking](#52-benchmarking)
6. [Real-World Use Cases](#6-real-world-use-cases)
   - [6.1 Caching](#61-caching)
   - [6.2 Rate Limiting](#62-rate-limiting)
   - [6.3 Session Store](#63-session-store)
   - [6.4 Leaderboard](#64-leaderboard)
7. [Cleanup and Shutdown](#7-cleanup-and-shutdown)
8. [Conclusion](#8-conclusion)
9. [References](#9-references)
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
tcp-backlog 511
timeout 0
tcp-keepalive 300
daemonize yes
supervised auto
pidfile /var/run/redis/redis-server.pid
loglevel notice
logfile /var/log/redis/redis-server.log
databases 16
always-show-logo yes
```
![image](https://github.com/user-attachments/assets/cfa5c160-c3fb-4d6d-8a65-dd2c8569b1ed)

### 1.3 Security Setup

**Set a Strong Password:**

```
requirepass your_strong_password
```

#### Disable Dangerous Commands

**To avoid accidental data loss:**

```
rename-command FLUSHDB ""
rename-command FLUSHALL ""
rename-command DEBUG ""
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

## 2. Basic Operations

### 2.1 Connecting to Redis

Use ```redis-cli``` to connect to your Redis server:

```
redis-cli -h localhost -p 6379 -a your_strong_password
```

### 2.2 String Operations

Redis strings are simple key-value pairs. Here are some common commands:
```
SET user:1:name "Komal Jaiswal"
GET user:1:name
MSET user:2:name "Komal Jaiswal" user:2:email "komal.jaiswal.snaatak@mygurukulam.co"
MGET user:2:name user:2:email
INCR visitor_count
EXPIRE user:1:session 3600
```
![image](https://github.com/user-attachments/assets/e7c6ddd0-3457-42c1-b7c7-63e5e854a77f)

### 2.3 List Operations

Redis lists are ordered collections of elements:
```
LPUSH latest_products "iPhone" "MacBook" "iPad"
RPUSH latest_products "AirPods"
LRANGE latest_products 0 -1
LPOP latest_products
RPOP latest_products
```
![image](https://github.com/user-attachments/assets/f1135c92-f987-40e5-a3a1-6b1555dc8961)

### 2.4 Hash Operations

Hashes are maps between string fields and string values:
```
HMSET user:3 username "Amit" email "amit.nagar.snaatak@mygurukulam.co" age 24
HGET user:3 username
HGETALL user:3
HINCRBY user:3 age 20
HDEL user:3 email
```
![image](https://github.com/user-attachments/assets/600b48d6-bb33-4ba2-99d2-5108af384a41)

### 2.5 Set Operations

Sets are collections of unique elements:
```
SADD popular_tags "technology" "programming" "database" "nosql"
SMEMBERS popular_tags
SISMEMBER popular_tags "nosql"
SREM popular_tags "nosql"
```
![image](https://github.com/user-attachments/assets/011ab3a0-5014-4718-9d31-e51d12586b57)

### 2.6 Sorted Set Operations

Sorted sets are like sets but with a score for each element:
```
ZADD leaderboard 1000 "player1" 985 "player2" 1200 "player3"
ZRANGE leaderboard 0 -1 WITHSCORES
ZRANK leaderboard "player2"
ZINCRBY leaderboard 15 "player2"
```
![image](https://github.com/user-attachments/assets/145dd02f-addc-4cfd-ba23-2fb71c945272)

## 3. Advanced Features

### 3.1 Pub/Sub Messaging

Redis Pub/Sub allows messaging between clients:

**Publisher (Terminal 1):**
```
PUBLISH news_channel "Breaking news: Redis 7.0 released!"
```
**Subscriber (Terminal 2):**
```
SUBSCRIBE news_channel
```
![image](https://github.com/user-attachments/assets/26b9caf2-780c-44fa-af0b-b13193ef44e7)

### 3.2 Transactions

Redis transactions ensure commands are executed as a batch:
```
MULTI
SET account:1:balance 1000
SET account:2:balance 500
INCRBY account:1:balance -100
INCRBY account:2:balance 100
EXEC
```
![image](https://github.com/user-attachments/assets/f16a1f1e-b61c-4119-98ad-ff5533b7d72d)

### 3.3 Lua Scripting

Use Lua scripts for complex operations:

```
EVAL "local key = KEYS[1]; local value = ARGV[1]; redis.call('SET', key, value); return redis.call('GET', key)" 1 mykey "Hello, Lua!"
```

![image](https://github.com/user-attachments/assets/ab9dd340-f2c9-44b6-8310-a9a6322a1a7a)

### 3.4 Pipelining

Pipelining allows sending multiple commands at once:
```
(echo -en "*1\r\n$4\r\nPING\r\n*1\r\n$4\r\nPING\r\n*1\r\n$4\r\nPING\r\n") | redis-cli -h localhost -p 6379 --pipe

```

### 3.5 Geospatial Operations

Redis supports geospatial data for location-based queries:

```
GEOADD locations 13.361389 38.115556 "Palermo" 15.087269 37.502669 "Catania"
GEODIST locations Palermo Catania km
GEORADIUS locations 15 37 100 km
```

## 4. Persistence Configuration

### 4.1 RDB (Redis Database)

Configure RDB snapshots to create periodic backups:
```
save 900 1
save 300 10
save 60 10000
dbfilename dump.rdb
dir /var/lib/redis
```

### 4.2 AOF (Append-Only File)

Enable AOF to log every write operation:

```
appendonly yes
appendfilename "appendonly.aof"
appendfsync everysec
```

## 5. Monitoring and Benchmarking

### 5.1 Monitoring

Monitor Redis operations and statistics:

```
redis-cli MONITOR
redis-cli INFO
```

### 5.2 Benchmarking

Benchmark Redis performance:
```
redis-benchmark -h localhost -p 6379 -a your_strong_password -t set,get -n 10000
```

## 6. Real-World Use Cases

### 6.1 Caching
Redis is often used to cache frequently accessed data to improve performance.

### 6.2 Rate Limiting
Redis can be used to implement rate limiting for APIs.

### 6.3 Session Store
Redis is commonly used to store user sessions due to its fast read/write operations.

### 6.4 Leaderboard
Redis is suitable for creating real-time leaderboards with sorted sets.

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
