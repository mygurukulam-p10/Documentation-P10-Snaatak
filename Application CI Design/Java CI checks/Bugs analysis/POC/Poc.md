# POC: Bugs Analysis

| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 25-09-2024         | 0.1       | Aayush Gaur  | Bugs Analysis              |

![spotbug](https://github.com/user-attachments/assets/3726e901-35ab-4378-b489-1cc9d1071d5d)

## Introduction
The Proof of Concept (POC) demonstrates the bug analysis process for the "salary-api" project from the OT-MICROSERVICES repository. This process focuses on identifying potential bugs and security vulnerabilities within the Java-based application 

## Prerequisites
- Java Version 17 (As per project dependency)
- Maven - A build automation tool used primarily for Java projects. It helps manage project dependencies, the build lifecycle, and project documentation.
- Spotbug - A static analysis tool that finds bugs in Java programs by analyzing bytecode.


## Steps 

### Install Java 17 and Maven
```
	sudo apt update
	sudo apt install openjdk-17-jdk
        sudo apt install maven
```
### Cloning Repo

```
git clone https://github.com/OT-MICROSERVICES/salary-api.git
```
### Add the Spotbug dependency in pom.xml file (present in salary api)


        <plugin>
          <groupId>com.github.spotbugs</groupId>
          <artifactId>spotbugs-maven-plugin</artifactId>
          <version>4.8.2.0</version>
          <dependencies>
            <dependency>
              <groupId>com.github.spotbugs</groupId>
              <artifactId>spotbugs</artifactId>
              <version>4.8.3</version>
            </dependency>
          </dependencies>
        </plugin>

### Integrate Find Security Bugs into spotbugs-maven-plugin

          <plugin>
              <groupId>com.github.spotbugs</groupId>
              <artifactId>spotbugs-maven-plugin</artifactId>
              <version>4.8.2.0</version>
              <configuration>
                  <includeFilterFile>spotbugs-security-include.xml</includeFilterFile>
                  <excludeFilterFile>spotbugs-security-exclude.xml</excludeFilterFile>
                  <plugins>
                      <plugin>
                          <groupId>com.h3xstream.findsecbugs</groupId>
                          <artifactId>findsecbugs-plugin</artifactId>
                          <version>1.12.0</version>
                      </plugin>
                  </plugins>
              </configuration>
          </plugin>

### Analyze Code with SpotBugs:
Run this command to check bugs

```
 mvn spotbugs:check
```

![Screenshot from 2024-09-28 13-17-35](https://github.com/user-attachments/assets/5b57037c-fc96-44df-871b-b2c1734ecd99)

### Generate SpotBugs Reports: 
Run this  command to generate an html report & it will  generate various types of reports, such as HTML and XML: (target/spotbugs.html)(target/spotbugsXml.xml).

```
mvn spotbugs:spotbugs
```

![Screenshot from 2024-09-28 13-24-48](https://github.com/user-attachments/assets/080df602-18b9-4f32-8b71-967fd3cfb6aa)



