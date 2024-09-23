# Understanding Commit Hooks in Git

![th](https://github.com/user-attachments/assets/2137c069-5ed0-4d5d-bd45-accb045fdba1)



## Table of Contents
1. [Introduction](#introduction)
2. [Purpose of Commit Hooks](#purpose-of-commit-hooks)
3. [Types of Commit Hooks](#types-of-commit-hooks)
4. [How to Use Git Hooks](#how-to-use-git-hooks)
5. [Example](#example)
6. [Frequently Asked Questions (FAQ)](#frequently-asked-questions-faq)
7. [Contact Information](#contact-information)
8. [References](#references)

## Introduction

**Git Hooks** are scripts that Git automatically executes before or after specific events occur in the Git workflow. These hooks are installed in a project's `.git/hooks` directory and are customizable to automate tasks like running tests, formatting code, sending notifications, or preventing certain actions.

<img width="370" alt="Git hook" src="https://github.com/user-attachments/assets/56361826-4d33-498c-9539-88bcd0abea7d">



### What are Commit Hooks?

Commit hooks are a subset of Git hooks triggered during the commit process. They ensure that specific rules are followed before code is committed, such as code formatting checks, commit message validation, or checking for sensitive data.

## Purpose of Commit Hooks

The primary purpose of commit hooks is to maintain the quality and consistency of code throughout the development lifecycle. Some common purposes include:
Automating Code Quality Checks:
- **Automating Code Quality Checks**: Automatically running linters, formatters, or tests before a commit.
- **Ensuring Consistent Commit Messages**: Enforcing commit message standards for better collaboration and history readability.
- **Preventing Common Mistakes**: Blocking commits with errors or sensitive data (e.g., API keys, credentials).
- **Streamlining Team Workflows**: Reducing manual tasks by automating repetitive actions.

## Types of Commit Hooks

Git supports several types of hooks for different stages of the commit process. The following are the primary commit hooks:

1. **Pre-Commit Hook**:
   - Triggered before the commit is created.
   - Commonly used to run tests, lint code, or check for trailing spaces.
   - Example: A hook to prevent a commit if there are syntax errors.

2. **Prepare-Commit-Message Hook**:
   - Triggered before the commit message editor opens.
   - Can be used to automatically add information to a commit message (e.g., ticket numbers).
   - Example: A hook to prepend a Jira issue number to every commit message.

3. **Commit-Message Hook**:
   - Triggered after the commit message is created but before the commit is finalized.
   - Used to validate commit messages against a regex pattern or check for certain keywords.
   - Example: A hook to enforce a commit message length limit.

4. **Post-Commit Hook**:
   - Triggered after the commit has been created.
   - Commonly used to notify a team or update a bug-tracking system.
   - Example: A hook to send a Slack notification after every commit.

## How to Use Git Hooks

### Step-by-Step Guide to Setting Up Git Hooks

1. **Locate the Hooks Directory**:
   - By default, hooks are stored in the `.git/hooks` directory of your repository.

2. **Create a New Hook Script**:
   - Create a new file named after the desired hook type, such as `pre-commit` or `commit-msg`.
   - Ensure the script file is executable (`chmod +x`).

3. **Write the Hook Script**:
   - Hooks can be written in any scripting language, but Bash is the most common.
   - Example of a `pre-commit` hook:
     ```bash
     #!/bin/bash
     # Check for trailing whitespace
     if git grep -q " $" --cached; then
       echo "Error: Trailing whitespace detected. Please remove it before committing."
       exit 1
     fi
     ```

4. **Test the Hook**:
   - Make changes to your repository, stage them, and try to commit.
   - If the hook script conditions are met, the commit will proceed; otherwise, it will block.

5. **Distribute Hooks (Optional)**:
   - Use tools like [Husky](https://typicode.github.io/husky) for JavaScript projects to manage hooks and ensure they run on all team members' machines.



### Example
#### Automatically Run Tests Before Committing

`Hook: pre-commit`

```#!/bin/bash
#This script runs tests before committing.
echo "Running tests..."
npm test
if [ $? -ne 0 ]; then
  echo "Tests failed. Aborting commit."
  exit 1
fi
```

### Example Usage

Save the script to `.git/hooks/pre-commit` in your repository.

Make it executable: `chmod +x .git/hooks/pre-commit`.

Attempt to commit changes; the script will run tests, and the commit will only proceed if they pass.


## Frequently Asked Questions (FAQ)

1. #### Can Git Hooks be shared across multiple repositories?
   Yes, you can create a shared hook directory outside the repository and configure it using the core.hooksPath setting in the .gitconfig file.

2. #### Are Git Hooks version-controlled?
   No, hooks are not version-controlled by default. You must distribute them manually or use tools like Husky.

3. #### Can hooks be bypassed?
   Yes, hooks can be bypassed using git commit --no-verify. However, this is not recommended for regular development practices.

4. #### Which programming languages can be used for Git Hooks?
   Hooks can be written in any language available on your system (e.g., Bash, Python). Bash is the most common choice.

5. #### How do I disable a hook temporarily?
   You can rename the hook script (e.g., pre-commit to pre-commit.disabled) or remove its executable permissions.

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
|https://www.atlassian.com/git/tutorials/git-hooks|Atlassian Git Hooks Guide|








