# Go CI Checks - Dependency Scanning


 ## Table of Contents

1. [Purpose](#purpose)
2. [Introduction](#introduction)
3. [What is Dependency Scanning](#what-is-dependency-scanning?)
4. [Different Tools for Go Dependency Scanning](#different-tools-for-go-dependency-scanning)
5. [Advantages and Disadvantages of Dependency Scanning](#advantages-and-disadvantages-of-dependency-scanning)
6. [Best Practices](#best-practices)
7. [Conclusion](#conclusion)
8. [Reference](#reference)
9. [Contact Information](#contact-information)

## Purpose

This document explains how to set up dependency scanning in Go projects, highlighting the use of Snyk as a key tool for identifying vulnerabilities during Continuous Integration (CI).

## Introduction

In Go projects, scanning for vulnerable dependencies is essential for maintaining security. Dependency scanning in CI pipeline helps detect potential risks in the external libraries that the project relies on, ensuring that codebase stays secure.

## What is Dependency Scanning?

Dependency scanning automatically analyzes the third-party libraries that project depends on, like those listed in go.mod and go.sum. The goal is to check for known security vulnerabilities and ensure that we’re using up-to-date and secure packages.


## Why Perform Dependency Scanning?

| **Reason**              |             **Description**                                |
|--------------------------------|-----------------------------------------------------|
| **Security**                | Identify and fix vulnerabilities in your dependencies. |
| **Compliance**              | Ensure compliance with security and licensing policies.|
| **Maintenance**             | Keep dependencies updated to avoid technical issues.|
| **Risk Management**         | Proactively manage risks from third-party code.  |

## Different Tools for Python Dependency Scanning and it's Comparision

| Tool              | Description                                               | Key Features                                   | License          | Integration                          | Pros                                          | Cons                                         |
|-------------------|-----------------------------------------------------------|------------------------------------------------|------------------|--------------------------------------|-----------------------------------------------|----------------------------------------------|
| **Snyk**        | Comprehensive vulnerability scanner for open-source dependencies. | - Monitors `go.mod`<br> - Provides fix suggestions | Free & Paid Plans | CLI, CI/CD, GitHub, GitLab           | - Large vulnerability database.<br> - Fix recommendations. | - Advanced features require a paid plan.     |
| **Dependabot**   | Automated dependency updates in GitHub.                   | - Auto PRs for updates.<br> - GitHub integration. | Free             | GitHub                               | - Automates dependency updates.               | - GitHub-only.                               |
| **GoVulnCheck**  | Checks Go modules for vulnerabilities.                   | - Scans `go.mod`.<br> - Simple reports.         | Open Source (Go Team) | CLI, CI/CD                           | - Native Go tool.                             | - Limited features.                          |
| **FOSSA**        | Security and license compliance scanner.                 | - Monitors for license compliance.<br> - Vulnerability reports. | Free & Paid Plans | CI/CD, GitHub, GitLab                | - Ideal for compliance-heavy projects.        | - Overly complex for smaller projects.       |

## Advantages and Disadvantages of Dependency Scanning