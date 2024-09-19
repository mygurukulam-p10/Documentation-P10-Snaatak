# Mutable and Immutable Infrastructure 🤔
=====================================

| 📅 CREATED/UPDATED | 📋 VERSION | 👨‍💻 AUTHOR | 📝 COMMENT |
|--------------------|------------|--------------|--------------------------------|
| 19-09-2024         | 0.2        | Brij Singh   | Mutable and Immutable Infrastructure              |

## Table of Contents
--------------------

* [Mutable Infrastructure 🏐](#mutable-infrastructure)
	+ [Definition](#definition)
	+ [Pros](#pros)
	+ [Cons](#cons)
* [Immutable Infrastructure 🔒](#immutable-infrastructure)
	+ [Definition](#definition-1)
	+ [Pros](#pros-1)
	+ [Cons](#cons-1)
* [Difference between Mutable and Immutable Infrastructure](#difference-between-mutable-and-immutable-infrastructure)
* [Contact Information](#contact-information)

## Mutable Infrastructure 🏐
---------------------------

### Definition

Mutable Infrastructure is the ability to change or mutate into something new. In the DevOps era, the advantage of mutability is critical when it comes to keeping past data without getting new infrastructure.

### Pros

* **Easy Troubleshooting 🚀**: You can understand each server on an individual basis, making it easier to troubleshoot issues.
* **Faster Updates ⏳**: Anyone can deploy updates to individual servers, which speeds up the updating process.
* **Customization 🎨**: You can verify that the infrastructure employed satisfies the unique requirements of each user.

### Cons

* **Update Failures 🚨**: Updates can fail for a variety of reasons, including DNS failure or bad network access, all of which require time to identify and resolve.
* **Configuration Drift 💧**: Each server’s configuration is unique, making it more difficult to diagnose and administer.
* **Debugging Issues 🖧**: Debugging is time-consuming due to update tracking issues. You may end up with many versions of an update with no understanding of the issue.
* **Lack of Documentation 📕**: Any changes you make to the server are not documented, making tracking difficult and debugging nearly impossible.

## Immutable Infrastructure 🔒
-----------------------------

### Definition

Immutable infrastructure is a model in which no upgrades, security patches, or configuration changes are made in place on production workloads. When a change is required, the architecture is constructed on new infrastructure and sent to production.

### Pros

* **Rollback Deployments 📙**: You can roll back deployments because earlier versions are unaffected.
* **Consistency 💯**: There is no middle zone in immutable infrastructure as the configurations on each server are consistent, and testing and rolling out upgrades are simplified.
* **Predictability 🔮**: You enjoy predictability since the servers stay the same. Ideal for interconnected environments, such as cloud technology.
* **Discrete Versioning 📈**: Each server version is independent of the others, and you will not have two versions running at the same time.

### Cons

* **No Modifications 🖫**: Existing servers cannot be modified. In the event of a malfunction, servers with the same configuration require a complete rebuild.
* **Data Storage 💾**: Instead of copying data to a local drive, you should store it outside in immutable infrastructure.
* **Provisioning and De-provisioning 📋**: Immutable Infrastructure is mostly based on virtualization, so there are some worries about provisioning and de-provisioning hardware and software as needed.

## Difference between Mutable and Immutable Infrastructure
--------------------------------------------------------

|  | Mutable Infrastructure | Immutable Infrastructure |
| --- | --- | --- |
| **Definition** | Ability to change or mutate into something new | State of being unchanged, never updated after deployment |
| **Updates** | No need to change the application code or apply a patch | Create a new image and deploy it as a replacement |
| **Server Changes** | Cloud resources can be changed, same server is utilized for updates, patches, and configuration changes | Can be changed, but not in the same server |
| **Configuration Drift** | Does not protect from configuration drift | Protected from configuration drift |

## Contact Information
---------------------

For any queries or further information, feel free to contact:

| 👨‍💻 Name | 📧 Email Address |
|---------------|-------------------------------------|
| **Brij Singh**| brij.singh.snaatak@mygurukulam.co   |

## References
--------------

* [1] "Mutable vs Immutable Infrastructure" by DevOps.com 📄
* [2] "Immutable Infrastructure: A Game-Changer for DevOps" by DZone 📄
