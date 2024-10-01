
# Proof of Concept (POC) for Secure Sockets Layer(SSL)
![image](https://github.com/user-attachments/assets/12313128-fc25-4cb4-b1e4-22b6a65a1018)


| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Vinay Bansal | 01-10-24 | version 1 | Vinay Bansal | 02-10-24 |

## 🔍 Purpose
We are preparing this document so that we can easily provide a completed guide to step up SSL using nginx.

  
## 📑 Table of Contents
- [📖Introduction](#introduction)
- [⚙️ Pre-Requisites](#-pre-requisites)
- [🖥️ System Requirements](#-system-requirements)
- [🚀 Run-Time Dependency](#-run-time-dependency)
- [🏗️ Architecture](#-architecture)
- [📥 Step-by-step Installation](#-step-by-step-installation)
- [📝Conclusion](#conclusion)
- [📧 Contact Information](#-contact-information )
- [📚 References](#-references )


## 📖Introduction 
In this document, I will show how to set up SSL using Nginx, include Pre-Requisites, System Requirements,Run-Time Dependency, Architecture. It is a security protocol that provides privacy, authentication, and data integrity for Internet communications.Integrating Cloudflare with Nginx for a DNS and SSL Proof of Concept (POC) can enhance security and performance.


## ⚙️ Pre-Requisites
- **Domain Name** Registered and managed by Cloudflare.
- **Server** A server running a Linux distribution (e.g., Ubuntu).
- **Nginx** Installed on your server.
- **Cloudflare Account** Set up and configured

## 🖥 System Requirements

| Hardware Specifications | Minimum Requirement  |
|--------------------------|------------------------|
| Processor                | Dual-core              |
| RAM                      | 1GB                    |
| Disk                     | 5GB                   |
| OS                       | Ubuntu(22.04)          |


## 🚀 Run-Time Dependency

| Name       | Version  | Description                                         |
|------------|----------|-----------------------------------------------------|
| Nginx       | 1.26.2  | Nginx handles SSL/TLS encryption |




## 🏗 Architecture
<img width="550" alt="image" src="https://github.com/user-attachments/assets/e1b932a4-a84b-4c9e-9887-9e8afdd6f955">



## 📥 Step-by-step Installation
### Step 1: Update DNS Settings
- Log in to your Cloudflare account.
- Add your domain and update your domain registrar to use Cloudflare’s nameservers.
  
###  Step 2: Install Nginx
```
sudo apt update
sudo apt install nginx
```
### Step 3: Obtain a Cloudflare Origin Certificate
- Go to the SSL/TLS section in your Cloudflare dashboard.
- Create an Origin Certificate.
- Save the certificate and private key to your server (e.g., cert.pem and key.pem).


### Step 4. Configure Nginx
- Edit your Nginx configuration to use the Cloudflare Origin Certificate
```
server {
    listen 443 ssl;
    server_name yourdomain.com;

    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/key.pem;

    location / {
        proxy_pass http://localhost:80;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```

### Step 5. Update Cloudflare SSL/TLS Settings
- In the Cloudflare dashboard, go to the SSL/TLS section.
- Set the SSL/TLS encryption mode to “Full (strict)”.

### Step 6. Test Nginx Configuration

```
sudo nginx -t
```

### Step 6. Check Cloudflare SSL Settings
- Check SSL Status: Ensure the SSL is active in the Cloudflare dashboard under the SSL/TLS tab

### Step 7. Restart Nginx
```
sudo systemctl restart nginx
```

### Step 8. Test Your Setup
**Visit https://yourdomain.com in your browser. You should see your site with a secure connection**

## 📝Conclusion
You now have SSL set up for your Nginx server using Cloudflare. This configuration enhances security and improves performance through Cloudflare's CDN.

##  📧 Contact Information
| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |



## 📚 References

| Title                                      | URL                                           |
|--------------------------------------------|-----------------------------------------------|
|Host a Website Using Cloudflare and Nginx|https://www.digitalocean.com/community/tutorials/how-to-host-a-website-using-cloudflare-and-nginx-on-ubuntu-20-04|
