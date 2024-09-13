![image](https://github.com/user-attachments/assets/cd7c1a71-31fa-4e97-b018-9aba2647f6fc)

# Gunicorn Documentation

## Table of Contents
1. [Introduction](#1-introduction)
2. [History](#2-history)
3. [Purpose and Benefits](#3-purpose-and-benefits)
4. [Advantages and Disadvantages](#4-advantages-and-disadvantages)
5. [Installation](#5-installation)
6. [Basic Usage](#6-basic-usage)
7. [Configuration](#7-configuration)
8. [Worker Types](#8-worker-types)
9. [Real-Life Example from Attendance API](#9-real-life-example-from-attendance-api)
10. [Alternatives to Gunicorn](#10-alternatives-to-gunicorn)
11. [Deployment Best Practices](#11-deployment-best-practices)
12. [Monitoring](#12-monitoring)
13. [Troubleshooting](#13-troubleshooting)
14. [Security Considerations](#14-security-considerations)
15. [Performance Tuning](#15-performance-tuning)
16. [References](#16-references)

## 1. Introduction
Gunicorn (Green Unicorn) is a Python Web Server Gateway Interface (WSGI) HTTP server for UNIX. It uses a pre-fork worker model, ported from Ruby's Unicorn project. Gunicorn is widely used to serve Python web applications due to its simplicity, performance, and flexibility.

## 2. History
Gunicorn was created by Benoit Chesneau and Paul J. Davis in 2010. Its name, "Green Unicorn," is a playful reference to Ruby's Unicorn server. Some key milestones include:

- **2010**: Initial release.
- **2013**: Version 18.0 released, introducing major performance improvements.
- **2019**: Version 20.0 released, adding support for Python 3.8 and dropping support for Python 2.6.
- **Ongoing**: Regular updates and maintenance by a dedicated community of contributors.

## 3. Purpose and Benefits

### Why Gunicorn is Used
Gunicorn serves as a bridge between your web application and the web server. It's primarily used for:

| **Category**      | **Description**                                                                                     |
|-------------------|-----------------------------------------------------------------------------------------------------|
| **Production-Ready** | Capable of handling concurrent requests efficiently.                                               |
| **Easy to Use**     | Simple setup with minimal configuration.                                                            |
| **Process Management** | Automatically manages worker processes, improving stability and resource utilization.              |
| **Compatibility**   | Works with a wide range of web frameworks like Django, Flask, and Pyramid.                          |
| **Performance**     | Handles a large number of simultaneous connections, suitable for high-traffic websites.              |

### Benefits of Gunicorn

| **Benefit**       | **Description**                                                                                     |
|-------------------|-----------------------------------------------------------------------------------------------------|
| **Scalability**   | Easily scale by adjusting the number of worker processes.                                            |
| **Flexibility**   | Supports various worker types (sync, async, gevent, etc.).                                          |
| **Reliability**   | Automatic worker process management ensures application uptime.                                      |
| **Security**      | Built-in protection against slowloris attacks and other vulnerabilities.                             |
| **Monitoring**    | Hooks for integrating with monitoring tools to track application performance.                        |

## 4. Advantages and Disadvantages

### Advantages
| Advantage           | Description                                                                                  |
|---------------------|----------------------------------------------------------------------------------------------|
| Production-Ready    | Designed for production environments, capable of handling high loads with stability.        |
| Easy to Use         | Simple to set up and configure, making it accessible for beginners.                         |
| Process Management  | Automatically manages worker processes, improving resource utilization and stability.       |
| Flexibility         | Supports multiple worker types, catering to different application needs.                    |
| Compatibility       | Compatible with major web frameworks such as Django, Flask, and Pyramid.                    |
| Scalability         | Easily scalable by adjusting the number of worker processes based on the application load.  |
| Security            | Provides built-in security features against common web server attacks.                      |

### Disadvantages
| Disadvantage            | Description                                                                                  |
|-------------------------|----------------------------------------------------------------------------------------------|
| UNIX-only               | Gunicorn is designed for UNIX systems and doesn't support Windows natively.                  |
| No Static File Handling | Not optimized for serving static files; typically requires a reverse proxy like Nginx.       |
| Single-threaded Workers | Default sync workers are single-threaded, not ideal for CPU-bound applications.              |
| Configuration Complexity| Advanced configuration options can become complex and difficult to manage.                   |
| Limited Protocol Support| Primarily supports HTTP/1.1; requires reverse proxies for HTTP/2 or WebSocket support.       |
| Potential for Slow Client Attacks | Vulnerable to certain types of slow client attacks if not properly configured.      |
| Resource Intensive      | Running multiple worker processes can consume significant memory, especially for large apps. |

## 5. Installation

To install Gunicorn, use the following command:

```
pip install gunicorn
```

## 6. Basic Usage 

To run a Python web application with Gunicorn, use the command:

```
gunicorn [OPTIONS] APP_MODULE
```

Where ```APP_MODULE``` is in format ```$(MODULE_NAME):$(VARIABLE_NAME)```

E.g. ``` gunicorn myapp:app ```

This command runs ```app``` object from ```myapp``` module.

## 7. Configuaration

Gunicorn can be configured via command-line arguments or a configuration file (`gunicorn.conf.py`). The configuration file path is typically located in the root of your project.

### Key Configuration Options

- `workers`: The number of worker processes.
- `worker_class`: The type of workers (e.g., sync, async).
- `bind`: The socket to bind (e.g., 0.0.0.0:8000).
- `timeout`: Maximum time (in seconds) a worker can take before it is restarted.

### Coniguration file ``` gunicorn.conf.py```

```
bind = '0.0.0.0:8000'
workers = 4
worker_class = 'sync'
timeout = 30
```

By default this conf file is not made we have to make that and if we want to use this configuartion file we have to define the path and use flag ```-c```.

## 8. Worker Types

Gunicorn supports various worker types to handle different application needs:

- **Sync Workers (default)**: Handles requests synchronously.
- **Async Workers**: Uses async libraries like `gevent` or `eventlet`.
- **Tornado Workers**: Uses Tornado, suitable for applications needing non-blocking I/O.

## 9. Real-Life Example from Attendance API

```
"""
Module for calling the main flask application.
The application will be only supported with Flask and Gunicorn.
"""
from flask import Flask, json
from flasgger import Swagger
from prometheus_flask_exporter import PrometheusMetrics
from router.attendance import route as create_record
from router.cache import cache
from utils.json_encoder import DataclassJSONEncoder
from client.redis.redis_conn import get_caching_data

app = Flask(__name__)

swagger = Swagger(app)

metrics = PrometheusMetrics(app)
metrics.info("attendance_api", "Attendance API opentelemetry metrics", version="0.1.0")

cache.init_app(app, get_caching_data())

app.config['JSON_SORT_KEYS'] = False
json.provider.DefaultJSONProvider.sort_keys = False
app.json_encoder = DataclassJSONEncoder

app.register_blueprint(create_record, url_prefix="/api/v1")

```

There is one file app.py which is used for gunicorn 

### To serve this application using Gunicorn, run

```
gunicorn app:app --log-config log.conf -b 0.0.0.0:8080

```
#### Explaination of Command 

- **`gunicorn`**: This is the command to start the Gunicorn WSGI HTTP server.

- **`app:app`**: This specifies the WSGI application to run. The format is `module:application`. In this case:
  - `app` is the name of the Python module (typically a file named `app.py`).
  - `app` is the WSGI application callable within that module.

- **`--log-config log.conf`**: This option tells Gunicorn to use a custom logging configuration defined in the `log.conf` file. This file specifies how logs should be handled, such as formatting, logging levels, and destinations (e.g., files, consoles).

- **`-b 0.0.0.0:8080`**: This option binds the server to the specified address and port:
  - `0.0.0.0` means that the server will listen on all available network interfaces.
  - `8080` is the port on which the server will listen for incoming connections.

## 10. Alternatives to Gunicorn

While Gunicorn is popular, there are several alternatives:

- **uWSGI**: Known for performance and extensive features.
- **Waitress**: A pure-Python WSGI server that works on Windows.
- **mod_wsgi**: An Apache module for hosting WSGI applications.
- **Tornado**: An asynchronous framework and WSGI server, good for long-lived connections.
- **Daphne**: Supports HTTP, HTTP2, and WebSocket protocols for ASGI and WSGI.

## 11. Deployment Best Practices

- **Use a Reverse Proxy**: Pair Gunicorn with Nginx or Apache for improved performance and security.
- **Optimize Worker Count**: Adjust the number of workers based on CPU count and application load.
- **Monitor Performance**: Utilize monitoring tools to keep an eye on Gunicorn's performance.

## 12. Monitoring

Gunicorn provides hooks for integrating with various monitoring tools, allowing you to track metrics like request rates, response times, and error rates.

## 13. Troubleshooting

Common issues and their solutions:

- **Worker Timeouts**: Increase the timeout setting if workers are timing out.
- **Memory Leaks**: Monitor memory usage; consider using `--preload` to identify memory leaks early.

## 14. Security Considerations

- **Run Gunicorn as a Non-Root User**: Avoid running Gunicorn as root for security reasons.
- **Limit Worker Resources**: Set appropriate resource limits for workers to prevent abuse.

## 15. Performance Tuning

- **Adjust Worker Type**: Use async workers for I/O-bound applications.
- **Optimize Worker Count**: More workers can handle more requests but also consume more memory.

## 16. References

| Reference                               | Description                                                                                         |
|-----------------------------------------|-----------------------------------------------------------------------------------------------------|
| [Official Gunicorn Documentation](https://docs.gunicorn.org/)            | Comprehensive guide on Gunicorn's features, configuration, and usage.                                 |
| [DigitalOcean Gunicorn Guide](https://www.digitalocean.com/community/tutorials/how-to-serve-flask-applications-with-gunicorn-and-nginx-on-ubuntu-22-04) | A step-by-step guide for deploying Flask apps with Gunicorn and Nginx on Ubuntu.                      |
| [Real Python Gunicorn Tutorial](https://realpython.com/flask-by-example-part-3-text-processing-with-redis-nokogiri-sinatra/) | A practical tutorial for deploying Python apps with Gunicorn, including examples and performance tips. |
| [Gunicorn History](https://gunicorn.org/#history)                      | A brief history of Gunicorn and its development milestones.                                           |
| [Benchmarking uWSGI vs Gunicorn](https://medium.com/@shubhayu7/benchmarking-uwsgi-vs-gunicorn-performance-4d82e2bf2e28) | Comparison of Gunicorn with uWSGI in terms of performance and scalability.                            |
| [Attendance API](https://github.com/OT-MICROSERVICES/attendance-api)  | The repository from where the Gunicorn is working and the app is running |



## Contact Information
|Name|Email Address|
|:---:|:---:|
|Komal|komal.jaiswal.snaatak@mygurukulam.co|
