# Understanding Commit Hooks in Git ![How to use pull request](https://github.com/user-attachments/assets/4650ceab-de1d-465f-84ab-147b836fda5e)




## Table of Contents
1. [Introduction](#introduction)
2. [Purpose of Commit Hooks](#purpose-of-commit-hooks)
3. [Types of Commit Hooks](#types-of-commit-hooks)
4. [How to use Commit Hooks](#how-to-use-commit-hooks)
5. [Contact Information](#contact-information)
6. [References](#references)
7. [Conclusion](#conclusion-of-commit-hooks)

## Introduction

**Git Hooks** are scripts that Git automatically executes before or after specific events occur in the Git workflow. These hooks are installed in a project's `.git/hooks` directory and are customizable to automate tasks like running tests, formatting code, sending notifications, or preventing certain actions.

<img width="370" alt="Git hook" src="https://github.com/user-attachments/assets/6bbb9890-e18c-4028-aa79-32472020308e">

### What are Commit Hooks?

Commit hooks are a subset of Git hooks triggered during the commit process. They ensure that specific rules are followed before code is committed, such as code formatting checks, commit message validation, or checking for sensitive data.

## Purpose of Commit Hooks

The primary purpose of commit hooks is to maintain the quality and consistency of code throughout the development lifecycle. Some common purposes include:
Automating Code Quality Checks:
| **Purpose**                                 | **Description**                                          |
|------------------------------------------------|------------------------------------------------------------|
| **Automating Code Quality Checks** | Automatically running linters, formatters, or tests before a commit. |
|**Ensuring Consistent Commit Messages**| Enforcing commit message standards for better collaboration and history readability.|
|**Preventing Common Mistakes**|Blocking commits with errors or sensitive data (e.g., API keys, credentials)|
|**Streamlining Team Workflows**|Reducing manual tasks by automating repetitive actions.|

## Types of Commit Hooks
Git supports several types of hooks for different stages of the commit process. The following are the primary commit hooks:
| **Types**                                 | **Description**                                          |
|------------------------------------------------|------------------------------------------------------------|
|  **Pre-Commit Hook** |  Triggered before the commit is created. Commonly used to run tests, lint code, or check for trailing spaces. |
|**Prepare-Commit-Message Hook**| Triggered before the commit message editor opens.Can be used to automatically add information to a commit message (e.g., ticket numbers).|
|**Commit-Message Hook**|Triggered after the commit message is created but before the commit is finalized. Used to validate commit messages against a regex pattern or check for certain keywords.|
|**Post-Commit Hook**|Triggered after the commit has been created.Commonly used to notify a team or update a bug-tracking system.|

## How to use Commit Hooks
To use commit hooks in Git, first navigate to the .git/hooks directory within your repository, where Git stores sample hook scripts. Choose the appropriate hook (such as pre-commit or commit-msg), and create a script with the desired commands (e.g., running tests or checking code style). Make the script executable by using the chmod +x command. When a commit action is performed, Git will automatically execute the corresponding hook script. This helps enforce consistent practices, such as validating commit messages or preventing flawed code from being committed. Hooks can be customized to fit the specific needs of your project or workflow.

## Contact Information
For more information, feedback, or assistance, feel free to contact us:
| Name         | Email address          |
|--------------|------------------------|
| Megha Tyagi          | megha.tyagi.snaatak@mygurukulam.co  |


## References
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
|https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks |Git Documentation - Customizing Git|
|https://git-scm.com/book/en/v2 | Pro Git Book - Git Hooks|

## Conclusion of Commit Hooks
Commit hooks (or Git hooks) are a powerful feature provided by Git that enables developers to automate tasks during various stages of the Git workflow. By providing custom scripts that execute automatically at key points in the commit lifecycle (like before or after a commit), commit hooks help enforce project standards, improve code quality, and streamline development processes.








