# Recomandation of Commit Hooks

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Megha Tyagi | 12-09-24 | version 1 | Megha Tyagi | 13-09-24 |

## Purpose 
This document aims to provide a comprehensive discussion on various types of commit hooks, highlighting their differences and recommending specific hooks based on their effectiveness and use cases. By understanding the unique purposes and functionalities of each commit hook, readers will gain insights into why certain hooks are recommended over others, ultimately aiding in the selection of the most suitable commit hooks for their development workflows.

## Table of Contents

1. [Introduction](#introduction)
2. [Types of Commit Hooks Overview](#types-of-commit-hooks-overview)
   - [Client-Side Commit Hooks](#client-side-commit-hooks)
   - [Server-Side Commit Hooks](#server-side-commit-hooks)
3. [Recommendations for Using Hooks](#recommendations-for-using-hooks)
   - [Pre-Commit Hook](#pre-commit-hook)
   - [Post-Commit Hook](#post-commit-hooks)
4. [Conclusion](#conclusion)
5. [Contact Information](#contact-information)
6. [References](#references)
   
## Introduction
Commit hooks are a type of Git hook that are automatically triggered during the commit process to enforce predefined rules and standards within a development environment. These hooks help maintain code quality and consistency by performing various checks before code changes are committed to the repository. Common uses of commit hooks include verifying code formatting, validating commit messages, detecting sensitive data, running automated tests, and ensuring compliance with project guidelines. By integrating commit hooks into the development workflow, teams can catch errors early, reduce manual code reviews, and maintain a higher standard of code integrity and security.

## Types of Commit Hooks Overview
![image](https://github.com/user-attachments/assets/20d4f97c-a4bb-4757-bbb9-489032063cfe)

### Client-Side Commit Hooks

| Hook Type           | Trigger                                              | Purpose                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| **Pre-commit**      | Runs before the commit is created.                  | Used for tasks like code formatting checks, linting, or running tests to ensure code quality. |
| **Prepare-commit-msg** | Runs after the pre-commit hook but before the commit message editor opens. | Automatically modifies or pre-populates the commit message (e.g., adding issue numbers or templates). |
| **Commit-msg**      | Runs after the commit message is entered but before the commit is finalized. | Validates the commit message format or content to adhere to specific guidelines or standards. |
| **Post-commit**     | Runs after the commit is successfully created.      | Used for notifications, logging, or triggering external services like CI/CD pipelines. |
| **Pre-push**        | Runs before changes are pushed to the remote repository. | Validates or performs checks (e.g., running tests) before code is pushed to the remote server. |

### Server-Side Commit Hooks

| Hook Type           | Trigger                                              | Purpose                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| **Pre-receive**     | Runs on the remote server before any updates are applied to the repository. | Ensures that incoming changes meet the repository's policies and standards (e.g., access controls, testing). |
| **Update**          | Runs on the remote server once for each branch that is being updated. | Used to enforce branch-specific checks and controls before accepting the changes. |
| **Post-receive**    | Runs on the remote server after the changes have been successfully received and applied. | Used for notifications, deployment scripts, or triggering further actions such as updating external systems. |

### Recommendations for Using Hooks

1. ##### Pre-Commit Hook

**Purpose:** The pre-commit hook runs before the commit is created. It is designed to check the code quality before the commit is finalized.

**Why Choose Pre-commit Hook:**
Choosing a pre-commit hook is crucial for maintaining high code quality and preventing errors. By utilizing this hook, you can ensure that code formatting checks, linting, and basic tests are performed before a commit is created. This process guarantees that only code that meets your quality standards is committed, thereby reducing the likelihood of introducing errors or style issues. Developers receive immediate feedback if their code does not adhere to the required standards, enabling them to address and correct issues before finalizing the commit. This proactive approach helps in preventing commits with errors or poor practices from being pushed to the repository, resulting in a cleaner and more reliable codebase.

**Essential pre-commit git hooks:**
| Hook Type           | Purpose                                             | Benefits                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------------------------|
| Code Formatting     | Automatically format code to adhere to style guidelines. | Ensures consistent code style, reducing formatting errors.|
| Linting         | Check for potential issues or coding errors.| Identifies and fixes potential issues before they are committed.|
|Basic Tests|Execute basic tests to verify code functionality.|Prevents committing code that fails existing tests.|
|Dependency Checks|Ensure all dependencies are properly defined and updated.|Avoids issues related to missing or outdated dependencies.|


2. ##### Post-Commit Hook

**Purpose:** The post-commit hook runs after the commit is successfully created. It is used for tasks that are better handled after the commit is finalized.

**Why Choose Post-commit Hook:**
The post-commit hook is particularly valuable for automating various tasks following a successful commit. It excels at automating actions such as sending notifications or triggering deployment pipelines, which streamlines the development process and enhances efficiency. Additionally, post-commit hooks are useful for logging commit details or notifying team members about recent commits, thereby improving collaboration and transparency within the team. They also enable the execution of scripts or tools that rely on the commit being finalized. For example, you can use post-commit hooks to update external systems or initiate more complex integration tests, ensuring that all dependencies and integrations are up-to-date and functioning correctly.

**Essential post-commit git hooks:**
| Hook Type           | Purpose                                             | Benefits                                                            |
|---------------------|------------------------------------------------------|--------------------------------------------------|
| Notifications     | Sends alerts or messages about recent commits to team members.| EKeeps the team informed about changes and updates.|
| Log Management        | Records commit details in logs for auditing and tracking purposes.| Provides historical context and traceability for commits.|
|CI/CD Triggers|Initiates continuous integration or deployment processes.|Automatically builds and deploys code after a commit.|
|Post-commit Actions|Executes additional scripts or tools that require a finalized commit.|Allows for complex actions or integrations post-commit.|

## Conclusion
Implementing pre-commit and post-commit hooks is crucial for maintaining high code quality and efficient development workflows. Pre-commit hooks focus on code formatting, linting, and running tests to ensure that only high-quality code gets committed. Post-commit hooks handle automation tasks such as triggering CI/CD pipelines, sending notifications, and updating external systems.

## Contact Information

| Name | Email address|
|------|---------------------|
| Megha Tyagi | megha.tyagi.snaatak@mygurukulam.co |

## References
For further reading and resources on Commit Hooks, check out the following:

| Links | Descriptions|
|------|---------------------|
|(https://devdynamics.ai/blog/untitled-2/)| **DevDynamics** |
|https://unstop.com/blog/git-hooks | **Unstop** |
|https://suthagar23.medium.com/git-hooks-keep-the-code-quality-119e6feb511e|**Medium**|


