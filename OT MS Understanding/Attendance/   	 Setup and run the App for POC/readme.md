| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Amit Nagar  | 06-09-24    | version 1  | Amit Nagar      | 06-09-24       |

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


```
# Update package list and upgrade existing packages

sudo apt-get update && sudo apt-get upgrade -y
```
```
# Install PostgreSQL

sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get install -y postgresql postgresql-contrib
sudo systemctl enable postgresql
sudo systemctl start postgresql
```
```

# Install Redis
sudo add-apt-repository ppa:redislabs/redis -y
sudo apt-get update
sudo apt-get install -y redis-server
sudo systemctl enable redis-server
sudo systemctl start redis-server
```
```
# Install Migrate

curl -L https://packagecloud.io/golang-migrate/migrate/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/migrate-keyring.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/migrate-keyring.gpg] https://packagecloud.io/golang-migrate/migrate/ubuntu/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/migrate.list
sudo apt-get update
sudo apt-get install -y migrate
```
```
# Install Poetry

curl -sSL https://install.python-poetry.org | python3 -
export PATH="$HOME/.local/bin:$PATH"
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
```
```
# Install Liquibase

wget -O- https://repo.liquibase.com/liquibase.asc | gpg --dearmor > liquibase-keyring.gpg
cat liquibase-keyring.gpg | sudo tee /usr/share/keyrings/liquibase-keyring.gpg > /dev/null
echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/liquibase-keyring.gpg] https://repo.liquibase.com stable main' | sudo tee /etc/apt/sources.list.d/liquibase.list
sudo apt-get update
sudo apt-get install -y liquibase
```
```
# Install Java 17

sudo apt-get install -y openjdk-17-jdk
sudo update-alternatives --set java /usr/lib/jvm/java-17-openjdk-amd64/bin/java
```
```
# Install Python 3.11

sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt-get update
sudo apt-get install -y python3.11 python3.11-venv python3.11-dev
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.11 1
sudo update-alternatives --set python3 /usr/bin/python3.11
```
```
# Install pip for Python 3.11

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.11 get-pip.py
rm get-pip.py
```
```
# Verify installations

psql --version
redis-server --version
migrate -version
poetry --version
liquibase --version
java -version
python3 --version
pip3 --version
```

