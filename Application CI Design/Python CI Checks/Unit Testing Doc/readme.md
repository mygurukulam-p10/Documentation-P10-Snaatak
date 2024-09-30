# Documentation of Unit Testing for Python
![python](https://github.com/user-attachments/assets/b67f3abf-d7e8-4022-8f39-9c534df7bd53)



  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Vinay Bansal | 23-09-24 | version 1 | Vinay Bansal | 24-09-24 |

## Purpose
The purpose of this document is to provide a comprehensive overview of Python Unit Testing, including its importance, tools available, best practices, and recommendations for efficient compilation processes.

  ## Table of Contents

- [Introduction](#introduction)
- [What are Unit Testing?](#what-are-unit-testing)
- [Why Unit Testing?](#why-unit-testing)
- [Different Tools for Unit Testing in Python](#different-tools-for-unit-testing-in-python)
- [Comparison of Tools](#comparison-of-tools)
- [Advantages](#advantages)
- [Disadvantages](#disadvantages)
- [Best Practices](#best-practices)
- [Recommendation](#recommendation)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)

# Introduction
Continuous Integration (CI) is a development practice that encourages developers to integrate their code into a shared repository frequently. Unit testing is a critical part of the software development process, ensuring that individual components of your application function as expected. This project showcases how to use unit tests in Python.

# What are Unit Testing?
Unit testing involves testing individual components (or units) of code to verify that they perform as expected. In Python, this often involves testing functions, methods, or classes to ensure they return the correct results given a set of inputs.

# Why Unit Testing?

| **Benefit**                  | **Description**                                                                  |
|------------------------------|---------------------------------------------------------------------------------|
| **Early Bug Detection**      | Catch issues before they reach production.                                      |
| **Documentation**            | Unit tests serve as a form of documentation for how the code is supposed to behave. |
|**Regression Testing**| They help in regression testing by verifying that previously fixed bugs don’t reappear.|
| **Modularity**          | To make code testable, developers often break it down into smaller, more manageable pieces. |


# Different Tools for Unit Testing in Python
- **Unittest**
- **Pytest**
 - **Doctest**
- **Coverage.py**


# Comparison of Tools
| Feature           | unittest                            | pytest                            | doctest                           | coverage.py                      |
|-------------------|------------------------------------|-----------------------------------|-----------------------------------|----------------------------------|
| **Type**          | Built-in Python testing framework  | Third-party testing framework     | Test embedded in docstrings       | Code coverage tool               |
| **Syntax**        | Class-based                        | Function-based, class-based, and more | Simple assertions in docstrings    | Requires decorators for tracking  |
| **Test Discovery**| Manual discovery                   | Automatic discovery                | Manual; runs on docstring parsing  | Not applicable                   |
| **Plugins**       | Limited                            | Extensive plugin system            | None                              | None                             |
| **Output**        | Text-based                         | Rich and customizable              | Text-based                        | Coverage reports (HTML, XML)     |
| **Parameterization**| Limited to subclasses             | Built-in support for parameterization | Not available                     | Not applicable                   |
| **Compatibility**  | Python standard library            | Python 3.6+                       | Python standard library            | Python 2.7 and 3.6+             |
| **Use Case**      | Basic unit testing                 | Complex testing scenarios, fixtures | Testing examples and docstrings    | Measuring code coverage          |

# Advantages

| **Feature**              | **Description**                                                                 |
|----------------------------|---------------------------------------------------------------------------------|
| **Automated Testing**      | Tests run automatically on every code push, catching issues early.            |
| **Quality Assurance**      | Consistent testing leads to a higher quality codebase.                        |
| **Faster Feedback Loop**   | Developers receive immediate feedback on their changes, allowing for quicker iterations. |

# Disadvantages
| **Aspect**                  | **Description**                                                                                      |
|-----------------------------|------------------------------------------------------------------------------------------------------|
| **Learning Curve**          | For beginners, pytest can have a steeper learning curve compared to simpler testing frameworks, especially with its advanced features and plugins. |
| **Mocking Complexity**      | Extensive use of mocking can complicate tests and make them harder to read and understand. |
| **Dependency Management**   | Managing dependencies in tests can lead to challenges |


# Best Practices

| **Best Practice**              | **Description**                                                                 |
|--------------------------------|---------------------------------------------------------------------------------|
| **Write Tests First**          | Adopt Test-Driven Development (TDD) where possible.                            |
| **Keep Tests Independent**     | Ensure each test runs independently of others.                                 |
| **Use Descriptive Names**      | Name your tests clearly to indicate their purpose.                             |
| **Run Tests Frequently**       | Integrate tests into your CI pipeline to run automatically.                   |


# Recommendation
## **pytest**
| Feature                     | Description                                                                                   |
|-----------------------------|-----------------------------------------------------------------------------------------------|
| **Simplicity and Readability** | pytest allows for writing simple and easy-to-read tests. Its syntax is straightforward, making it accessible for beginners. |
| **Rich Features**           | Supports fixtures, parameterized testing, and plugins, significantly enhancing testing capabilities. |
| **Flexible Test Discovery** | Automatically discovers tests based on naming conventions, saving time in test organization. |


# Conclusion
Using `pytest` as your testing framework significantly enhances your testing strategy by providing a flexible and easy-to-use interface. Its features promote good testing practices, allowing for better code quality and maintainability. Embracing `pytest` in your development process, along with effective CI practices, ensures a robust and reliable codebase.

# Contact Information

| Name | Email address|
|------|---------------------|
| Vinay Bansal | vinay.bansal.snaatak@mygurukulam.co |

# References
For further reading and resources on GitOps, check out the following:

| Links | Descriptions|
|------|---------------------|
|https://www.datacamp.com/tutorial/pytest-tutorial-a-hands-on-guide-to-unit-testing|Pytest|
|https://medium.com/@dirk.avery/pytest-modulenotfounderror-no-module-named-requests-a770e6926ac5|ModuleNotFoundError|
