# Detailed Redis Proof of Concept (POC) Guide

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
8. [References](#8-references)

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

#### Enable SSL/TLS (if needed)

**Configure Redis to use SSL/TLS for secure connections:**

```
tls-port 6380
tls-cert-file /path/to/cert.pem
tls-key-file /path/to/key.pem
tls-ca-cert-file /path/to/ca.pem
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
SET user:1:name "John Doe"
GET user:1:name
MSET user:2:name "Jane Smith" user:2:email "jane@example.com"
MGET user:2:name user:2:email
INCR visitor_count
EXPIRE user:1:session 3600
TTL user:1:session
```


