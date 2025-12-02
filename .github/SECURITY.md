# Security Policy for FilmFetch-Automated-Movie-Indexer-Service

This document outlines the vulnerability reporting process for the `FilmFetch-Automated-Movie-Indexer-Service` repository, maintained by @chirag127.

## 1. Security Philosophy (Apex Mandate)

As an Apex Technical Authority project, security is treated as a first-class citizen, aligning with the "Zero-Defect, Future-Proof" philosophy. We adhere to strict input validation, dependency auditing, and secure configuration standards.

## 2. Supported Versions

This project primarily utilizes **Python 3.10+** and modern dependency managers (**uv**). We actively track and patch vulnerabilities in direct dependencies listed in `pyproject.toml`. We generally support the latest stable Python patch releases for the current major version (e.g., 3.12.x, 3.11.x).

## 3. Reporting a Vulnerability

If you discover any vulnerability or security concern in this repository, please follow these responsible disclosure steps immediately. **Do not create a public issue first.**

### Step 1: Private Disclosure

Immediately contact the maintainer via email with the subject line: `[SECURITY] Vulnerability Report - FilmFetch-Automated-Movie-Indexer-Service`.

**Maintainer Contact:**

*   **Email:** `security@chirag127.dev` (or similar designated security contact if one exists, otherwise use the primary contact method specified in the repo).

### Step 2: Provide Necessary Details

In your private report, include:

1.  **Project Context:** State clearly that the report concerns `FilmFetch-Automated-Movie-Indexer-Service`.
2.  **Vulnerability Type:** (e.g., RCE, Injection, Information Leak, Dependency Flaw).
3.  **Affected Component:** Specify the part of the service (e.g., Usenet parser, configuration loading, CLI argument handling).
4.  **Steps to Reproduce (PoC):** Provide clear, step-by-step instructions to replicate the issue.
5.  **Severity Assessment:** Your estimate of the impact (Low, Medium, High, Critical).

### Step 3: Awaiting Response

We commit to acknowledging receipt of your report within **48 hours**. We will work with you privately to develop and test a fix. Public disclosure will only occur after a patch has been released to mitigate the risk.

## 4. Vulnerable Dependencies & Scanning

We enforce dependency auditing using the following automated measures:

*   **Dependency Scanning:** GitHub Dependabot is configured to automatically monitor for known vulnerabilities in Python packages listed in `pyproject.toml`.
*   **CI Enforcement:** The primary CI workflow (`.github/workflows/ci.yml`) runs security checks against project dependencies as part of the required pipeline stages.

## 5. Secret Management

**API Keys and Credentials:**

*   This service frequently requires external API keys (e.g., for download clients, Usenet providers, or potential future AI services).
*   **NEVER** commit secrets, keys, or tokens to this repository. All credentials must be supplied via **Environment Variables** when running the application or deployment pipelines.
*   We use GitHub Secrets for CI/CD processes, ensuring secrets are never exposed in logs or artifact storage.

## 6. Future Scope: Bug Bounties

Currently, this project operates under a responsible disclosure policy without a formal bug bounty program. However, contributions leading to significant security improvements are always recognized via GitHub contributions.