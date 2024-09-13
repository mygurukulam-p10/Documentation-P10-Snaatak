# Gunicorn: Simple Proof of Concept

## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
   - [System Requirements](#system-requirements)
   - [Dependencies](#dependencies)
   - [Important Ports](#important-ports)
3. [Architecture](#architecture)
4. [Step-by-step installation](#step-by-step-installation)
5. [Monitoring](#monitoring)
   - [Metrics](#metrics)
   - [Health Check](#health-check)
   - [Logging](#logging)
6. [Troubleshooting](#troubleshooting)
7. [FAQs](#faqs)
8. [Contact Information](#contact-information)
9. [References](#references)

## Purpose
This Proof of Concept (POC) demonstrates the basic setup and usage of Gunicorn, a WSGI HTTP Server for Python applications. It aims to show how to deploy a simple Flask application using Gunicorn, highlighting its key features and benefits.

## Pre-requisites

### System Requirements

| Hardware Specifications | Minimum Recommendation |
|-------------------------|------------------------|
| Processor               | Dual-core              |
| RAM                     | 4GB                    |
| Disk                    | 20GB                   |
| OS                      | Ubuntu 22.04           |

### Dependencies

| Name     | Version | Description                              |
|----------|---------|------------------------------------------|
| Python   | 3.8+    | Programming language for the application |
| pip      | 20.0+   | Package installer for Python             |
| Gunicorn | 20.1.0  | WSGI HTTP Server                         |
| Flask    | 2.0.1   | Web framework for Python                 |

### Important Ports

| Inbound Traffic | Description     |
|-----------------|-----------------|
| 8000            | Used by Gunicorn|

## Architecture

```mermaid
graph TD
    A[Client] -->|HTTP Request| B[Gunicorn]
    B -->|Forward Request| C[Flask Application]
    C -->|Process Request| D[Application Logic]
    D -->|Generate Response| C
    C -->|Return Response| B
    B -->|HTTP Response| A
```

This simple architecture illustrates:
1. Client sends an HTTP request to Gunicorn.
2. Gunicorn forwards the request to the Flask application.
3. The Flask application processes the request and generates a response.
4. Gunicorn sends the response back to the client.

## Step-by-step installation

### Step 1: System Preparation

```bash
# Update system packages
sudo apt update && sudo apt upgrade -y

# Install Python and pip
sudo apt install -y python3 python3-pip
```

### Step 2: Create a Virtual Environment

```bash
# Create a project directory
mkdir myapp && cd myapp

# Create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
# Upgrade pip
pip install --upgrade pip

# Install Gunicorn and Flask
pip install gunicorn flask
```

### Step 4: Create a Sample Flask Application

Create a file named `app.py`:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello, Gunicorn!"

@app.route('/health')
def health():
    return "OK", 200

if __name__ == '__main__':
    app.run()
```

### Step 5: Run the Application with Gunicorn

```bash
gunicorn --workers 3 --bind 0.0.0.0:8000 app:app
```

## Monitoring

### Metrics

| Parameter        | Description                                | Priority | Threshold |
|------------------|--------------------------------------------|----------|-----------|
| CPU Utilization  | CPU usage by Gunicorn workers              | High     | < 80%     |
| Memory Usage     | Memory consumption by Gunicorn processes   | High     | < 80%     |
| Request Rate     | Number of requests handled per second      | High     | Varies    |
| Response Time    | Time taken to respond to requests          | High     | < 200ms   |

### Health Check

| Name     | Type           | InitialDelaySeconds | PeriodSeconds | TimeoutSeconds | SuccessThreshold | FailureThreshold |
|----------|----------------|----------------------|---------------|----------------|------------------|------------------|
| App      | HTTP GET /health | 5                    | 10            | 2              | 1                | 3                |

### Logging

| Log Type      | Description                                 |
|---------------|---------------------------------------------|
| Gunicorn Logs | Access and error logs (stdout/stderr)       |

## Troubleshooting

1. **Gunicorn fails to start**: 
   - Check if the port is already in use: `sudo lsof -i :8000`
   - Verify Python dependencies are installed correctly

2. **High response times**:
   - Monitor CPU and memory usage
   - Consider increasing the number of worker processes

3. **Worker timeout issues**:
   - Adjust the timeout setting when starting Gunicorn
   - Optimize the application code for faster responses

## FAQs

1. **How many Gunicorn workers should I use?**
   A common rule of thumb is `(2 x $num_cores) + 1`, but this can be adjusted based on your specific workload and available resources.

2. **Can Gunicorn handle WebSocket connections?**
   Yes, Gunicorn can handle WebSocket connections when used with compatible frameworks and the appropriate worker class.

3. **Is Gunicorn suitable for production use?**
   Yes, Gunicorn is widely used in production environments. However, for production, you might want to consider additional components like a reverse proxy for added features and security.

## Contact Information

| Name        | Email Address                          |
|-------------|----------------------------------------|
| Amit Nagar  | amit.nagar.snaatak@mygurukulam.co      |

## References

| Links                                            | Descriptions                         |
|--------------------------------------------------|--------------------------------------|
| https://docs.gunicorn.org/                       | Official Gunicorn documentation      |
| https://flask.palletsprojects.com/               | Flask documentation                  |
| https://docs.python.org/3/library/venv.html      | Python virtual environments guide    |
