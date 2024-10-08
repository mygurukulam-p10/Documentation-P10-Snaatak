# 💥 OpenVPN Installation and Configuration Guide


| Author      | Created on   | Version | Last updated by | Last edited on  |
|-------------|--------------|---------|-----------------|-----------------|
| Amit Nagar  | 8-10-2024   | 1.0     | Amit Nagar      | 09-10-2024      |

---

## 📚 Table of Contents

1. [Introduction](#Introduction)
2. [Pre-requisites](#⚙-pre-requisites)
3. [System Requirements](#🔍-system-requirements)
4. [Steps to Install and Configure OpenVPN](#💥-steps-to-install-and-configure-openvpn)
5. [Conclusion](#conclusion)
6. [Contact](#contact)
7. [References](#references)

📚 Introduction
This document serves as a comprehensive guide for installing and configuring OpenVPN, aimed at simplifying the setup process for users of all skill levels. 

---
## ⚙ Pre-requisites

## 🔍 System Requirements

| Specification                    | Requirement                         |
|----------------------------------|-------------------------------------|
| **CPU**                          | 1 CPU core |
| **RAM**                          | Minimum of 512 MB (1 GB recommended). |
| **Disk Space**                  | At least 10 GB of free disk space. |
| **Operating System**            | Ubuntu 20.04+ |


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

- **VPN Protocol**: Choose between UDP or TCP. UDP is recommended for better performance.
- **Port Number**: Enter the port number you want OpenVPN to listen on. The default is 1194.
- **DNS Server**: Choose the DNS server to use. Popular choices include Google DNS, OpenDNS, or Cloudflare.
- **Encryption Strength**: Select the desired encryption level. A higher encryption strength ensures better security but may reduce performance.
- **Client Name**: Enter a name for the first VPN client configuration (e.g., client1).

After selecting the options, the script will install OpenVPN and generate the server and client configuration files.

## 5. Generate a Client Configuration File

After installation, the script will prompt you to create a client configuration file. This file will have a .ovpn extension (e.g., client1.ovpn).

You can generate additional client configuration files later by running the script again:

```bash
./openvpn-install.sh
```

When prompted, choose the option to add a new user and enter the desired client name.

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
sudo openvpn --config client.ovpn
```

## 8. Verifying the OpenVPN Installation

To verify that the VPN is working correctly:

- **Check Your IP Address**: Use a service like whatismyip.com before and after connecting to the VPN to see if your IP address has changed.
- **Ping the VPN Server**: Verify connectivity by pinging your VPN server's private IP address.


## Conclusion

You have successfully set up OpenVPN using a script! You can now securely connect to your VPN server and manage connections. For more advanced configurations, refer to the official OpenVPN documentation or explore the settings in the server configuration file (`/etc/openvpn/server.conf`).
