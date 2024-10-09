# 💥 OpenVPN Installation and Configuration Guide


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 08-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |

---

## 📚 Table of Contents

1. [Introduction](#Introduction)
2. [Pre-requisites](#⚙-pre-requisites)
3. [System Requirements](#🔍-system-requirements)
4. [Steps to Install and Configure OpenVPN](#💥-steps-to-install-and-configure-openvpn)
5. [Conclusion](#conclusion)
6. [Contact Information](#-contact-information)
7. [References](#references)

## 📚 Introduction
This document serves as a comprehensive guide for installing and configuring OpenVPN.

---
## ⚙ Pre-requisites

## 🔍 System Requirements

| Specification                    | Requirement                         |
|----------------------------------|-------------------------------------|
| **CPU**                          | 1 CPU core |
| **RAM**                          | Minimum of 512 MB (1 GB recommended). |
| **Disk Space**                  | At least 10 GB of free disk space. |
| **Operating System**            | Ubuntu 22.04 |


---

## 💥 Steps to Install and Configure OpenVPN

### 1. Download the OpenVPN Installation Script

Download the OpenVPN installation script from the official repository:

```bash
curl -O https://raw.githubusercontent.com/angristan/openvpn-install/master/openvpn-install.sh
```

## 2. Make the Script Executable

Change the permissions of the downloaded script to make it executable:

```bash
chmod +x openvpn-install.sh
```

This step ensures that the script can be run as a program.

## 3. Run the OpenVPN Installation Script

Run the script to install OpenVPN:

```bash
./openvpn-install.sh
```

The script will check for dependencies, install necessary packages, and guide you through the setup process.

## 4. Follow the On-Screen Prompts

During the script execution, you will be prompted to choose several options:


### 4.1 Assign a public IP address to your OpenVPN server
![Screenshot from 2024-10-08 19-15-18](https://github.com/user-attachments/assets/fb33f3b0-84e4-405e-9f68-e6f34b740a8b)
![Screenshot from 2024-10-08 19-17-38](https://github.com/user-attachments/assets/b165eec0-d1b1-4324-91b7-dc3d907e0d6c)

### 4.2 VPN Protocol
Choose between UDP or TCP. UDP is recommended for better performance.
![Screenshot from 2024-10-08 19-18-20](https://github.com/user-attachments/assets/8494dc17-ae5c-4a86-92a3-771d1c4ae7a4)

### 4.3 Port Number
Enter the port number you want OpenVPN to listen on. The default is 1194.
![Screenshot from 2024-10-08 19-18-20](https://github.com/user-attachments/assets/66536745-c557-4362-a132-1ec6e43d8474)

### 4.4 DNS Server
Choose the DNS server to use. Popular choices include Google DNS, OpenDNS, or Cloudflare.
![Screenshot from 2024-10-08 19-18-52](https://github.com/user-attachments/assets/4f0c0a11-4ee5-43e7-b5ae-b93dd90946be)

### 4.5 Encryption Strength
Select the desired encryption level. A higher encryption strength ensures better security but may reduce performance.
![Screenshot from 2024-10-08 19-19-27](https://github.com/user-attachments/assets/337431ea-7747-4779-ba7a-ca0d233b46b6)

### 4.6 Client Name
Enter a name for the first VPN client configuration (e.g., client1).
![Screenshot from 2024-10-08 19-22-07](https://github.com/user-attachments/assets/9b644f04-5931-4374-b926-88af56533338)

## 5. Generate a Client Configuration File

After installation, the script will prompt you to create a client configuration file. This file will have a .ovpn extension (e.g., client1.ovpn).
![Screenshot from 2024-10-08 19-22-54](https://github.com/user-attachments/assets/a5496401-100a-451d-9509-142f9590af41)

## 6. Download the Client Configuration File

Once the client configuration file is created, download it to your local machine using scp:

```bash
scp user@your-server-ip:/path/to/client.ovpn .
```

Replace `user@your-server-ip` and `/path/to/client.ovpn` with your server's username, IP address, and the actual path to the client configuration file.

## 7. Connect to OpenVPN

Use the generated .ovpn file to connect to the VPN from your OpenVPN client.


### On Windows

1. Install the OpenVPN GUI.
2. Place the .ovpn file in the `C:\Program Files\OpenVPN\config` directory.
3. Open the OpenVPN GUI and connect using the client configuration file.

### On Linux

Run the following command to connect to the VPN:

```bash
sudo openvpn --config openvpn_otms.ovpn
```
![Screenshot from 2024-10-08 19-37-22](https://github.com/user-attachments/assets/ef08cfc2-7c87-42f9-b0cd-a64a56889a19)

![Screenshot from 2024-10-08 19-37-27](https://github.com/user-attachments/assets/1d64af76-57da-4d85-9180-af4182660e21)

## 8. Verifying the OpenVPN Installation

To verify that the VPN is working correctly:


- **Check Your IP Address**: Use a service like whatismyip.com before and after connecting to the VPN to see if your IP address has changed.
- **Ping the VPN Server**: Verify connectivity by pinging your VPN server's private IP address.
![Screenshot from 2024-10-08 19-38-13](https://github.com/user-attachments/assets/b5c8c9ad-d798-4435-8918-a8a8d7f9a159)

![Screenshot from 2024-10-09 01-26-53](https://github.com/user-attachments/assets/f1686c87-4ef1-4abb-b0c8-67fee1985861)

## Conclusion

You have successfully set up OpenVPN using a script! You can now securely connect to your VPN server and manage connections.


## 📧 Contact Information

| Name       | Email Address                              |
|------------|--------------------------------------------|
| Amit Nagar | amit.nagar.snaatak@mygurukulam.com       |

## 📚 References

| Topic                            | Reference Link                                                       |
|----------------------------------|---------------------------------------------------------------------|
| OpenVPN Documentation            | [OpenVPN Official Documentation](https://openvpn.net/community-resources/documentation/) |
| OpenVPN GitHub Repository        | [OpenVPN GitHub Repository](https://github.com/OpenVPN/openvpn)    |
| OpenVPN Installation Script      | [OpenVPN Install Script](https://github.com/angristan/openvpn-install) |
| Network Configuration            | [Network Configuration for VPN](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-20-04) | 

