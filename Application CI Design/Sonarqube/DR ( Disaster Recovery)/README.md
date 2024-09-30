# 🛠️ SonarQube Disaster Recovery Plan

| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Komal       | 26-09-24    | Version 1  | Komal Jaiswal   | 29-09-24       |


## 📑 Table of Contents
1. [🎯 Purpose](#purpose)
2. [📖 Overview](#overview)
3. [🔐 Backup Procedures](#backup-procedures)
   - [📂 Database Backup](#database-backup)
   - [🛠️ Configuration Backup](#configuration-backup)
   - [🔍 Elasticsearch Data Backup (Optional)](#elasticsearch-data-backup-optional)
4. [♻️ Restoration Procedures](#restoration-procedures)
   - [💾 Database Restoration](#database-restoration)
   - [🔧 Configuration Restoration](#configuration-restoration)
   - [📊 Elasticsearch Data Restoration (Optional)](#elasticsearch-data-restoration-optional)
5. [⏱️ Mean Time to Recovery (MTTR)](#mean-time-to-recovery-mttr)
6. [🚨 Disaster Recovery Testing](#disaster-recovery-testing)
7. [📞 Contact](#contact)
8. [🔗 References](#references)

---

## 🎯 Purpose
This document provides a detailed plan for ensuring the quick and effective recovery of SonarQube in the event of a system failure or disaster. The goal is to minimize downtime and data loss while ensuring Appliction continuity through clear backup and restoration procedures.

---

## 📖 Overview
The Disaster Recovery (DR) plan focuses on SonarQube's database, configuration files, and optional Elasticsearch data. This plan ensures that in the case of failure, all critical SonarQube data can be restored quickly.

---

## 🔐 Backup Procedures

### 📂 Database Backup
Backup the SonarQube PostgreSQL database to ensure that critical data is preserved.

#### 1. Command to Backup SonarQube Database.

```
pg_dump -U postgres sonarqube > /home/ubuntu/backup/sonarqube_backup.sql
``` 

#### 2. Verify the Backup
```
ls /home/ubuntu/backup/sonarqube_backup.sql
```

#### 3. Automate daily backup using Cron

```
crontab -e

Add Line below to backup the database every midnight.

0 0 * * * pg_dump -U postgres sonarqube > /path/to/backup/sonarqube_backup_$(date +\%F).sql

```

### 🛠️ Configuration Backup

1. Backup the SonarQube configuration files, including `sonar.properties` and `wrapper.conf`.
```
cp /opt/sonarqube/conf/sonar.properties /home/ubuntu/backup/sonar.properties
cp /opt/sonarqube/conf/wrapper.conf /home/ubuntu/backup/wrapper.conf
```

## ♻️ Restoration Procedures

### 💾 Database Restoration

Step-by-step guide to restore the PostgreSQL database.

#### 1. Stop the SonatQube service 

```
sudo systemctl stop sonarqube
```

#### 2. Drop the Existing Database 

```
psql -U postgres -c "DROP DATABASE sonarqube;"
```

#### 3. Recreate the SonarQube Database 

```
psql -U postgres -c "CREATE DATABASE sonarqube;"
```

#### 4. Restore the database from backup

```
psql -U postgres sonarqube < /home/ubuntu/backup/sonarqube_backup.sql
```
 
### 🔧 Configuration Restoration
Restore the SonarQube configuration files to their original state.

1. Restore the configuration files.

```
cp /path/to/backup/sonar.properties /opt/sonarqube/conf/sonar.properties
cp /path/to/backup/wrapper.conf /opt/sonarqube/conf/wrapper.conf
```

## ⏱️ Mean Time to Recovery (MTTR)

MTTR estimates the time to fully restore SonarQube after a failure. The time breakdown is as follows:

### 💾 Database Restoration:
- **Stop service**: ~1 minute
- **Restore database** (~2GB): ~5–10 minutes
- **Start SonarQube**: ~2 minutes
- **Total time**: ~8–13 minutes

### 🔧 Configuration Restoration:
- **Copy configuration**: ~1–2 minutes
- **Total time**: ~2–3 minutes

### 📊 Optional Elasticsearch Data Restoration:
- **Copy Elasticsearch data**: ~3–5 minutes
- **Total time**: ~3–5 minutes

### ⏳ **Estimated MTTR**:
**~15–20 minutes** (depending on the size of the data).


## 🚨 Disaster Recovery Testing
Regular testing procedures to ensure that the backup and restoration processes work as expected, reducing the risk of extended downtime.

1. **Simulate a failure by stopping SonarQube:**

```
sudo systemctl stop sonarqube
```

2. **Restore database and configuration files from the latest backups.**

3. **Restart SonarQube**

```
sudo systemctl start sonarqube
```

4. Verify restoration by accessing SonarQube at ```http://<your-server-ip>:9000 ``` and checking if all projects and configurations are intact.   
---


## 🔗 References
- [SonarQube Documentation](https://docs.sonarqube.org/)
- [PostgreSQL Backup and Restore](https://www.postgresql.org/docs/current/backup-dump.html)


## 📧 Contact Information

For more information on how to implement or if you need any guidance, feel free to reach out:

| Name  | Email Address                                  |
|-------|------------------------------------------------|
| Komal | komal.jaiswal.snaatak@mygurukulam.co           |
