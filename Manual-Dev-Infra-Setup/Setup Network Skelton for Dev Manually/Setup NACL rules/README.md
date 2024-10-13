# 🌐 Setup AWS Network Access Control List (NACL) Rules - Documentation

| Author      | Created on | Version   | Last updated by | Last edited on | Reviewed By L0 | Reviewed By L1 | Reviewed By L2 |
|-------------|------------|-----------|-----------------|----------------|----------------|----------------|----------------| 
| Komal       | 03-10-24   | Version 1 | Komal Jaiswal   | 06-10-24       |                |                |                |

---

## 📝 Table of Contents
1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [Key Features of NACLs](#key-features-of-nacls)
4. [Benefits of Using NACLs](#benefits-of-using-nacls)
5. [Setup NACL Rules for DEV-Infra](#setup-nacl-rules-for-dev-infra)
   - [Inbound Rules](#inbound-rules)
   - [Outbound Rules](#outbound-rules)
6. [Conclusion](#conclusion)
7. [References](#references)
8. [Contact Information](#contact-information)

---

## 📜 Purpose
This documentation provides guidelines for setting up **Network Access Control Lists (NACLs)** in AWS. NACLs act as stateless firewalls at the subnet level, enabling users to control access to and from subnets with rules for inbound and outbound traffic.

---

## 📖 Introduction
**AWS Network Access Control Lists (NACLs)** provide an additional layer of security for subnets within a VPC. Unlike Security Groups, which are applied at the instance level, NACLs are stateless and apply at the subnet level. This makes them ideal for handling broad access control policies, allowing specific IP ranges, protocols, and ports to be either allowed or denied access.

---

## 🔑 Key Features of NACLs

- **Stateless Traffic Filtering**: Unlike Security Groups, NACLs do not remember request state, meaning both inbound and outbound rules must be defined separately.
- **Custom Rule Definition**: NACLs allow granular control over IP ranges, protocols, and port ranges for subnets.
- **Ordered Rule Evaluation**: NACL rules are evaluated in ascending order, starting from the lowest numbered rule until a match is found.
- **Default Deny Rule**: Any traffic not explicitly allowed by the rules will be denied by default.

---

## 🎯 Benefits of Using NACLs

- **Subnet-Level Security**: Apply broad access control policies at the subnet level for consistency and ease of management.
- **Enhanced Security Layers**: Offers an additional layer of protection by providing fine-grained control of traffic across subnets.
- **Flexibility in Rule Creation**: NACLs enable easy creation of multiple rules to allow or deny traffic based on source/destination IPs and port ranges.
- **Customizable Access Control**: Allows setting custom rules to adapt to unique networking requirements, providing flexibility in managing access.

---

## 🛠 Setup NACL Rules for DEV-Infra

### Inbound Rules
1. Navigate to **VPC Dashboard** in the AWS Console.
2. Under **Network ACLs**, select or create a new **NACL** for the subnet.
3. Click on **Inbound Rules** and set up rules with:
   - **Rule Number**: Define the priority order for rule evaluation (lower numbers take precedence).
   - **Type**: Select protocol (e.g., HTTP, SSH, or Custom Protocol).
   - **Source**: Define the allowed IP address or CIDR block for incoming traffic.
   - **Port Range**: Specify the port range to allow or deny traffic.
   - **Allow/Deny**: Choose to either **allow** or **deny** the traffic.

### Outbound Rules
1. Under the **Outbound Rules** tab, set rules similar to inbound for outbound traffic:
   - **Rule Number**: Determine priority for outbound traffic (lower numbers take precedence).
   - **Type**: Select the protocol (e.g., TCP, UDP, or Custom Protocol).
   - **Destination**: Define IP address or CIDR block for allowed destinations.
   - **Port Range**: Specify the range to control outbound traffic.
   - **Allow/Deny**: Select whether to **allow** or **deny** the traffic.


### Public-NACL
#### Inbound Rules
![image](https://github.com/user-attachments/assets/c48df4e1-0ae7-4911-a90d-96239694d03e)

#### OutBound Rules
![image](https://github.com/user-attachments/assets/5f421b33-b0bb-48e5-be9b-c1b4c2fc280b)

#### Subnet Association
![image](https://github.com/user-attachments/assets/78f90579-0fe3-40b0-839a-ba2c7b07468c)

### Frontend-NACL
![image](https://github.com/user-attachments/assets/f4784c04-4511-4593-8b88-c5444b775949)

#### Inbound Rules
![image](https://github.com/user-attachments/assets/ee3a7fc0-d4fe-4bd5-a754-409f36e5bedf)

#### OutBound Rules
![image](https://github.com/user-attachments/assets/92e82b0a-ea63-43e3-9d84-b0234e987730)


#### Subnet Association
![image](https://github.com/user-attachments/assets/f235699b-cde6-4c8b-89d0-248b3bcf19c3)


### Application NACL
![image](https://github.com/user-attachments/assets/72f59e04-f74c-4f9b-8c3c-53ec6ddec4f0)

#### Inbound Rules
![image](https://github.com/user-attachments/assets/f963b66e-14c9-4ea8-9d3e-6baddf64cde0)

#### OutBound Rules
![image](https://github.com/user-attachments/assets/dd0f90f5-fc57-46f1-b00a-15ce2c6d2af6)

#### Subnet Association
![image](https://github.com/user-attachments/assets/f1690798-189d-401c-8b2c-0bd866b29175)

### Database NACL
![image](https://github.com/user-attachments/assets/0c76161b-2e03-4805-adb8-de5c0217db86)

#### Inbound Rules
![image](https://github.com/user-attachments/assets/cab92a9d-a29b-46f6-b212-f5afcfe8f1a2)

#### OutBound Rules
![image](https://github.com/user-attachments/assets/5a91543f-5e54-45df-b7db-70ae92713ceb)

#### Subnet Association
![image](https://github.com/user-attachments/assets/92e1aedf-f590-477a-844c-1c0719cbeeb3)


---

## 🔚 Conclusion

AWS Network Access Control Lists (NACLs) provide users with granular control over traffic at the subnet level, enhancing security and adding flexibility to network configurations. By strategically configuring inbound and outbound rules, users can create secure, efficient, and customized network environments within AWS, protecting sensitive data and applications.

---

## 📚 References

| Reference                                   | Link                                                                                                  |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| AWS Documentation                           | [Amazon VPC Documentation](https://docs.aws.amazon.com/vpc/index.html)                               |
| Network ACLs                                | [Working with NACLs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)         |

---

## 📞 Contact Information

| Name             | Email                        | Phone           |
|------------------|------------------------------|-----------------|
| Komal Jaiswal    | komal.jaiswal@example.com    | +1 (555) 123-4567 |

