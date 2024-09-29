## POC of DNS

|  Author        | Created on |  Version  | Last updated by   |   Last edited on   |
|----------------|------------|-----------|-------------------|--------------------|
| Abhinav Singh  |  19-09-24  | version 2 |   Abhinav Singh   |      26-09-24      |


## Table of Contents
1. [Purpose](#purpose)
2. [Pre-requisites](#pre-requisites)
3. [Step by Step DNS Setup](#step-by-step-DNS-setup)
4. [Conclusion](#conclusion)
5. [Contact Information](#Contact-Information)
6. [References](#References)

## Purpose

This README outlines the POC for implementing DNS for an application. It demonstrates how to purchase a domain, configure DNS records, and set up a DNS server for the application. The document includes step-by-step instructions, important considerations for performance and security.


## Prerequisites

Below are the prerequisites required before setting up your application:

| Prerequisite                   | Description                                                                                  |
|---------------------------------|----------------------------------------------------------------------------------------------|
| **Registered Domain Name**      | A domain name purchased from a domain registrar like Namecheap or GoDaddy.                   |
| **Cloudflare Account**          | A free or paid account on Cloudflare.                                                        |
| **Application Server (Optional)** | If you plan to host your application using an IP address, a server with a known IP address. |



## Step by Step DNS Setup

**1. Create an account on your choosen Domain Registrar which i am using Namechap** 

![image](https://github.com/user-attachments/assets/3990ca70-ba28-4959-9536-f9f2904d9931)


**2. Click on Domains and search for your domain Availability**

![image](https://github.com/user-attachments/assets/40fe1234-db99-4bee-99e5-8c8c545bda62)


**3. Choose Domain you want among the list of Domains and add it to your account cart.**
![image](https://github.com/user-attachments/assets/5b2b471d-412d-4056-87f8-a7686bca9862)


**4. In your cart Section Click on checkout to purchase the Domain**


![image](https://github.com/user-attachments/assets/03a5e74d-30a8-40cf-9db7-f3e2c4b973d4)


**5. Complete the payment and confirm the order to buy the Domain and You will get the Domain.**

![image](https://github.com/user-attachments/assets/afc426e6-337f-473a-9208-978f65ee443d)


**6. Login to your Cloudflare Account**

![image](https://github.com/user-attachments/assets/c9deb623-45b4-4730-ac41-8a54387b2fb2)

**7. On your dashboard choose "Add site" option on the top right corner of the page.**

![image](https://github.com/user-attachments/assets/40133ea3-89ef-4aed-be46-ced4dd4ce348)

**8. Enter your purchased domain in the existing Domain field and choose Continue.**

![image](https://github.com/user-attachments/assets/8c6afa0b-e248-4985-8278-dbc7477eabe7)

**9. Select a plan as per your requirement and choose continue.**

![image](https://github.com/user-attachments/assets/63b9c958-15d8-46c9-9c71-4ba48b9f15d8)

**10. You will be redirected to the home page where you can see that your domain got added.**

![image](https://github.com/user-attachments/assets/ec551352-fc81-43d3-90f6-ef9b460ea16e)

**11. Choose your added domain, You will get ns values there that you need to copy.**

![image](https://github.com/user-attachments/assets/d7d1d420-cd7e-4180-aec7-23791007a0fe)

12. Move to Your Domain registrar and choose manage domain.

![image](https://github.com/user-attachments/assets/63ab4bcc-bc5f-4822-a19f-9cec656ec0ad)

**13. Choose custom DNS option and paste the nameserver values copied from Cloudflare and save.**

![image](https://github.com/user-attachments/assets/a9a2944e-43f5-43a2-9f8d-db8df66bb908)

![image](https://github.com/user-attachments/assets/012b2547-2e52-4cb6-ac35-1874b433778d)

It will take some time to get nameservers updated.

**14. Now move back to your cloudflare account and choose DNS option in left navigation bar.**

![image](https://github.com/user-attachments/assets/0dccc458-b19d-47ba-a97e-93943e4da456)

**15. Add a DNS record you want to add and choose for type of record you want to create.**

If you want to host your application using IP address of your application server then choose A type record and enter IP address of your server and simply save the record.

Also you can add a subdomain in Name section of your record.

![image](https://github.com/user-attachments/assets/dc943a9d-10fc-443b-a872-ecfa3d3bdb80)

**16. Search for your domain with DNS record and you will see your application hosted on it.**

![image](https://github.com/user-attachments/assets/70d17e30-ff29-49ad-a40a-fd096a10a87a)


## Conclusion
This proof of concept (POC) demonstrates the successful implementation of DNS for an application using Cloudflare as the DNS provider. The document outlines the steps involved, from purchasing a domain to configuring DNS records and setting up a DNS server.


## Contact Information

For more information on how to setup Github or if you need any guidance, feel free to reach out:

|  Name   | Email Address                                  |
|---------|------------------------------------------------|
| Abhinav | abhinav.singh.snaatak@mygurukulam.co           |


## Reference

|  Title   |                    Link                        |
|----------|------------------------------------------------|
|https://www.cloudflare.com/learning/dns/what-is-dns/|**CloudFlare**|
|https://www.hostinger.com/tutorials/what-is-dns| **Hostiger Tutorials**|
|https://en.wikipedia.org/wiki/OpenDNS|**Wikipedia**|
