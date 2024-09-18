
# 🚀 Project VCS Policies

This document outlines the version control system (VCS) policies for managing code in the repository. It includes naming conventions, commit message guidelines, and templates for branches and tags. By following these conventions, we aim to maintain consistency, readability, and traceability across the project.
| 📅 CREATED/UPDATED | 📌 VERSION | ✍️ AUTHOR    | 📝 COMMENT                     |
|--------------------|------------|--------------|--------------------------------|
| 16-09-2024         | 0.3        | Brij Singh   | Naming Conventions           |

## 📑 Table of Contents

1. [Naming Conventions](#naming-conventions)
    - [Branch Name Template](#branch-name-template)
    - [Tag Name Template](#tag-name-template)
    - [Commit Message Format](#commit-message-format)
2. [Detailed Documentation](#detailed-documentation)
3. [Contact Information](#contact-information)
4. [References](#references)

## 📛 Naming Conventions

To keep our repository clean, organized, and easy to navigate, we have established the following naming conventions for branches, tags, and commits.

### Branch Name Template

Branches are essential for working on isolated features, bug fixes, or experiments. Use a clear naming structure that reflects the purpose of the branch.


#### Branch Types:
 | **Name** | **Description** |
|--------------|-----------------|  
| **feature/**| Used for new features or enhancements.|
| **bugfix/**| Used for resolving bugs.|
| **hotfix/**| Used for urgent, high-priority fixes that need to go directly into production.|
| **release/**| Preparing for a new release.|
| **test/** |Used for testing purposes or experimentation.|



#### Examples:
- `feature/123-user-authentication`
- `bugfix/456-fix-404-error`
- `hotfix/789-critical-bugfix`
- `release/v2.0.0`

### Tag Name Template

Tags mark specific points in the repository’s history, typically for releases or important milestones. Use the following template for tags:

#### Examples:
- `v1.0.0`: First major release.
- `v1.1.0`: Minor feature updates and improvements.
- `v1.1.1`: Patch for bug fixes.



#### Commit Types:
| **Commit** | **Description** |
|--------------|-----------------| 
| **feat**| New feature or functionality.|
| **fix**| Bug fix.|
| **docs**| Documentation-only changes.|
| **style**| Code style changes (formatting, no code logic changes).|
| **refactor**| Code refactoring without adding new features or fixing bugs.|

| **chore**| Miscellaneous tasks, such as build tasks or dependency updates.|


## 📚 Detailed Documentation

For more detailed documentation on setting up and following the VCS policies in this project, please refer to the following sections in the repository's documentation:

- **VCS Workflow Guide**: Instructions on how to create branches, submit merge requests, and manage releases.
- **Commit Message Guidelines**: In-depth guidelines on writing effective commit messages.
- **Branch Management**: Best practices for managing branches and merging.
- **Release Process**: Step-by-step guide for creating and tagging releases.

Documentation can be found [here](https://dev.to/varbsan/a-simplified-convention-for-naming-branches-and-commits-in-git-il4).

:sparkles: Conclusion
Naming conventions for Git branches in automation testing projects play a vital role in facilitating collaboration and maintaining clarity. By following best practices such as using feature-based, bug-based, test suite-based, you can enhance the efficiency and effectiveness of your testing processes. Additionally, customizing the conventions to suit your team's specific needs promotes consistency and fosters better collaboration among team members. Remember, clear and descriptive branch names are key to efficient version control in automation testing projects.


## 📧 Contact Information

|Name|Email Address|
|:---:|:---:|
|Brij Singh|brij.singh.snaatak@mygurukulam.co|


## 📚 References

- [Git Branching Naming Best Practices](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)
- [Semantic Versioning](https://semver.org/)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)


