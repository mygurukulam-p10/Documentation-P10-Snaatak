# Domain Name System (DNS) Documentation  ![dns 2 (3)](https://github.com/user-attachments/assets/bb553ef8-6663-4cce-8602-da60b7ea7d20)


  

| ✍️Author      | 📅Created on  |📌 Version    | 📝Last updated by |📅 Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Megha Tyagi | 19-09-24    | Version 1  | Megha Tyagi     | 19-09-24       |

# Purpose 
This Readme provides a comprehensive overview of the Domain Name System (DNS) and its various providers. It explains what DNS is, why it is used, and how it works. The document also compares popular DNS providers, detailing their features and drawbacks, and recommends Cloudflare DNS based on its performance and privacy benefits. Additionally,it includes contact information for feedback and relevant resources for further reading.

## Table of Contents
1. [🔍 What is DNS?](#-what-is-dns)
2. [🚀 Why we use DNS?](#-why-we-use-dns)
3. [🖧 How does DNS Works?](#-how-does-dns-works)
4. [💥 Popular DNS Provider](#-popular-dns-provider)
   - [DNS Watch](#dns-watch)
   - [CloudFlare](#clouflare)
   - [OpenDNS](#opendns)
   - [Google Public DNS](#goggle-public-dns)
   - [5centsCDN](#5centscdn)
5. [📛 Detailed Comparision of DNS Providers](#-detailed-comparision-of-dns-providers)
6. [💯 Recommendation of Cloudflare DNS Provider](#-recommendation-of-cloudflare-dns-provider)
7. [Conclusion](#conclusion)
8. [📧 Contact Information](#-contact-information)
9. [📚 References](#-references)


## 🔍 What is DNS?
DNS (Domain Name System) is like the Internet's phonebook. It converts user-friendly domain names (like www.example.com) into IP addresses (like 192.168.1.1) that computers use to find each other online.

<img width="301" alt="image" src="https://github.com/user-attachments/assets/96f83dc3-2de6-43d7-9a46-2376143cdb38">


## 🚀 Why we use DNS?
We use DNS to simplify browsing the web. Instead of remembering and typing complex IP addresses, we use easy-to-remember domain names. DNS translates these names into IP addresses, allowing our browsers to locate and load websites quickly and efficiently.

## 🖧 How does DNS Works?
DNS resolution is the process of converting a website name (like www.facebook.com) into a computer-friendly IP address (like 217.64.213.12). Just like a street address helps find a house, an IP address helps locate the right device on the Internet. When you enter a website name, your browser automatically translates it into an IP address without you having to do anything. This happens behind the scenes, with your browser sending a request and the DNS system handling the rest.

![Untitled Diagram-Page-2 drawio](https://github.com/user-attachments/assets/c1816388-59df-416d-bee1-18f83d0e8026)

- When you request a domain name, your computer first checks its local cache to see if you've previously looked up the address recently; if not, a request to your Recursive DNS Server will be made.

- A Recursive DNS Server is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked up domain names. If a result is found locally, this is sent back to your computer, and your request ends here (this is common for popular and heavily requested services such as Google, Facebook, Twitter). If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet's root DNS servers.

- The root servers act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request. If, for example, you request "www.facebook.com", the root server will recognize the Top Level Domain of.com and refer you to the correct TLD server that deals with .com addresses.

- The TLD server holds records for where to find the authoritative server to answer the DNS request. The authoritative server is often also known as the nameserver for the domain. You'll often find multiple nameservers for a domain name to act as a backup in case one goes down.

- An authoritative DNS server is the server that is responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made. Depending on the record type, the DNS record is then sent back to the Recursive DNS Server, where a local copy will be cached for future requests and then relayed back to the original client that made the request. DNS records all come with a TTL (Time To Live) value. This value is a number represented in seconds that the response should be saved for locally until you have to look it up again. Caching saves on having to make a DNS request every time you communicate with a server.


## 💥 Popular DNS Provider

- ### DNS Watch :
  
  DNS.Watch is a smaller DNS provider, with a focus on privacy protection. Unlike most DNS providers, these guys don’t 
  keep records of your DNS lookups. That means that the log of your activities are not used for marketing purposes, sold 
  to other companies, or passed along to some spy agency. DNS.Watch does, however, record some anonymized data that is not 
  associated with particular users. It uses this data for “statistics and security research.”

- ### CloudFlare:
  
  Cloudflare DNS is a top-tier service known for its high performance, redundancy, and strong privacy protections. It 
  offers fast response times and never logs IP addresses or sells data for targeted ads. Cloudflare collaborates with KPMG 
  for annual audits to ensure security and reliability.

- ### OpenDNS:

  OpenDNS is a free service that separates your DNS operations from the ISP specified system to provide more reliable, 
  safer and faster internet access. OpenDNS connects to high-performance DNS serves and stores the IPs of millions of 
  sites in a cache to reduce the time it takes to resolve your requests. Setting up OpenDNS on your network or individual 
  PC/Android device is simple and free. You just need to configure device/router settings without any additional software.


- ### Google Public DNS:

  Google Public DNS is a global service that helps speed up and secure web browsing by handling DNS queries. It’s the 
  largest public DNS service, providing fast and reliable connections. Google also offers Google Cloud DNS for managing 
  and publishing domain names on the web.

- ### 5centsCDN:

  5centsCDN is a comprehensive Content Delivery Network (CDN) solution that empowers high-growth businesses to deliver 
  exceptional content experiences to a global audience. We cater specifically to enterprise-level organizations across 
  diverse industries, with a primary focus on the U.S., Latin America, India, the Middle East, Asia, and Africa. Our 
  platform is designed to meet the demanding needs of companies that prioritize branding, user experience, and scalability.


## 📛 Detailed Comparision of DNS Providers

|💡 **Provider**     | 🔄**Primary DNS** | 🔄**Secondary DNS** | 🌟**Features**                  | 🚨**Drawbacks**                                                                                           |
|------------------|-----------------|-------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **DNS Watch**        | 84.200.69.80    | 84.200.70.40      | - Privacy-focused, no tracking<br>- Fast resolution<br>- No logging                               | - Fewer advanced features compared to other providers<br>- Limited customer support                    |
| **Cloudflare**       | 1.1.1.1         | 1.0.0.1           | - Fast and secure<br>- No user tracking<br>- Privacy-focused<br>- DNS over HTTPS (DoH) support   | - May not offer as many advanced features for enterprise needs<br>- Some users may prefer more control|
| **OpenDNS**          | 208.67.222.222  | 208.67.220.220    | - Customizable security and content filtering<br>- Phishing protection<br>- Optional paid plans   | - Some features require a subscription<br>- Basic free plan might not have as much customization      |
| **Google Public DNS**| 8.8.8.8         | 8.8.4.4           | - Fast and reliable<br>- Google’s infrastructure<br>- DNS over HTTPS (DoH) support                | - Google collects some data on queries<br>- Privacy concerns due to association with Google            |
| **5centsCDN**        | 185.228.168.9   | 185.228.169.9     | - Ad-free DNS<br>- Privacy-focused<br>- Fast resolution<br>- DNS over HTTPS (DoH) support         | - Smaller provider with less visibility<br>- May not have as robust infrastructure as larger providers |


## 💯 Recommendation of Cloudflare DNS Provider

| ✅**Reason**                  |📄 **Details**                                                                                                         |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Speed and Performance**   | Cloudflare DNS offers some of the fastest DNS resolution times, ensuring quick access to websites and online services. |
| **Privacy and Security**    | Cloudflare prioritizes privacy with no tracking of user data and supports DNS over HTTPS (DoH) to encrypt DNS queries, enhancing security. |
| **Reliability**             | Leveraging Cloudflare’s extensive global network, it provides high availability and minimal downtime, making it a reliable choice. |
| **Free and Accessible**     | The DNS service is free to use, offering high-quality performance without requiring a subscription, making it accessible for various users. |
| **Additional Features**     | Cloudflare offers extra features like DNS filtering and enhanced security options (in paid plans), adding versatility for different needs. |
| **Industry Reputation**     | Cloudflare is a well-known and trusted name in the industry, known for its strong infrastructure and commitment to improving internet performance. |

# Conclusion:
This documentation explains the Domain Name System (DNS), its purpose, functionality, and popular providers. It compares providers like DNS Watch, Cloudflare, OpenDNS, Google Public DNS, and 5centsCDN, highlighting their features and drawbacks. Cloudflare DNS stands out for its speed, privacy, and security. With DNS over HTTPS (DoH) and no user tracking, it offers reliable performance. Overall, Cloudflare is recommended for its trusted infrastructure and broad appeal for users.

## 📧 Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi  | megha.tyagi.snaatak@mygurukulam.co  |


## 📚 References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://www.cloudflare.com/learning/dns/what-is-dns/|**CloudFlare**|
|https://www.hostinger.com/tutorials/what-is-dns| **Hostiger Tutorials**|
|https://en.wikipedia.org/wiki/OpenDNS|**Wikipedia**|
|https://blokt.com/guides/best-dns-servers|**Blokt**|

