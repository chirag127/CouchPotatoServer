# Contributing to FilmFetch-Automated-Movie-Indexer-Service

Thank you for considering contributing to `FilmFetch-Automated-Movie-Indexer-Service`! Your input and contributions are vital to enhancing this robust, scalable media workflow automation and intelligent content acquisition engine.

We welcome contributions from everyone, whether you're a seasoned developer, a beginner, or just keen to improve the project. This document outlines the guidelines for contributing to ensure a smooth and effective collaboration.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Forking and Cloning the Repository](#forking-and-cloning-the-repository)
  - [Setting Up Your Development Environment](#setting-up-your-development-environment)
- [Making Changes](#making-changes)
  - [Branching Strategy](#branching-strategy)
  - [Coding Style](#coding-style)
  - [Commit Guidelines](#commit-guidelines)
  - [Testing](#testing)
  - [Linting and Formatting](#linting-and-formatting)
- [Submitting Changes](#submitting-changes)
  - [Pull Request Process](#pull-request-process)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)
- [Security Vulnerabilities](#security-vulnerabilities)

## Code of Conduct

We adhere to a professional and inclusive [Code of Conduct](https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/blob/main/CODE_OF_CONDUCT.md). Please review it to understand our community standards and expectations.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

*   **Python 3.10+**: Download and install from [python.org](https://www.python.org/downloads/).
*   **uv**: A fast Python package installer and resolver. Install it via `curl -LsSf https://astral.sh/uv/install.sh | sh` or `pip install uv`.
*   **Git**: For version control.

### Forking and Cloning the Repository

1.  **Fork** the repository by clicking the 'Fork' button on the top right of the [FilmFetch-Automated-Movie-Indexer-Service GitHub page](https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service).
2.  **Clone** your forked repository to your local machine:

    bash
    git clone https://github.com/YOUR_GITHUB_USERNAME/FilmFetch-Automated-Movie-Indexer-Service.git
    cd FilmFetch-Automated-Movie-Indexer-Service
    

3.  Add the upstream repository as a remote:

    bash
    git remote add upstream https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service.git
    

### Setting Up Your Development Environment

1.  **Create a virtual environment** using `uv`:

    bash
    uv venv
    

2.  **Activate** the virtual environment:

    *   On macOS/Linux:
        bash
        source .venv/bin/activate
        
    *   On Windows:
        bash
        .venv\Scripts\activate
        

3.  **Install project dependencies** (including development dependencies):

    bash
    uv pip install -e '.[dev]'
    

## Making Changes

### Branching Strategy

We use a feature-branch workflow:

1.  Always start your work from the `main` branch, ensuring it's up-to-date:

    bash
    git checkout main
    git pull upstream main
    

2.  Create a new, descriptively named branch for your feature or bug fix:

    bash
    git checkout -b feature/your-feature-name 
    # or fix/your-bug-fix-name
    

### Coding Style

*   Adhere to Python's [PEP 8](https://www.python.org/dev/peps/pep-0008/) style guide.
*   We use `Ruff` for linting and formatting, which enforces a consistent code style. Your code will be automatically checked during CI/CD.

### Commit Guidelines

We encourage using [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for clear, descriptive commit messages. This helps with automatic changelog generation and understanding the project history.

Examples:

*   `feat: Add new movie indexing source for streaming platforms`
*   `fix: Resolve issue with NZB download client integration`
*   `docs: Update contributing guidelines with uv setup`
*   `refactor(api): Improve error handling in content acquisition module`

### Testing

*   All new features and bug fixes should be accompanied by relevant unit and/or integration tests using `pytest`.
*   Ensure existing tests pass before submitting your changes.
*   Run tests from the project root:

    bash
    pytest
    

*   To run tests with coverage:

    bash
    pytest --cov=filmfetch
    

### Linting and Formatting

Before committing, ensure your code passes `Ruff` checks and is properly formatted:

1.  **Run Ruff linter and formatter:**

    bash
    ruff check .
    ruff format .
    

2.  To automatically fix many linting issues and format your code:

    bash
    ruff check . --fix
    ruff format .
    

## Submitting Changes

### Pull Request Process

1.  Once your changes are complete, committed, and all tests pass, push your branch to your forked repository:

    bash
    git push origin feature/your-feature-name
    

2.  Go to the [FilmFetch-Automated-Movie-Indexer-Service GitHub page](https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service) and open a new Pull Request (PR) from your forked branch to the `main` branch of the upstream repository.
3.  **Fill out the Pull Request template** (`.github/PULL_REQUEST_TEMPLATE.md`) comprehensively. Clearly describe the changes, rationale, and any related issues.
4.  Our CI/CD pipeline will automatically run tests and linting checks. Address any failures promptly.
5.  Your PR will be reviewed by a core maintainer. Be responsive to feedback and be prepared to make further adjustments.

## Reporting Bugs

If you find a bug, please open an issue using our [bug report template](https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/blob/main/.github/ISSUE_TEMPLATE/bug_report.md). Provide as much detail as possible, including:

*   A clear and concise description of the bug.
*   Steps to reproduce the behavior.
*   Expected behavior.
*   Screenshots or error messages, if applicable.
*   Your operating system and Python version.

## Suggesting Enhancements

We welcome ideas for new features or improvements. Open a new issue and clearly describe:

*   The problem you're trying to solve.
*   Your proposed solution or enhancement.
*   Any alternatives you've considered.
*   How this would benefit the project and its users.

## Security Vulnerabilities

If you discover any security vulnerabilities, please do **NOT** open a public issue. Instead, refer to our [Security Policy](https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/blob/main/.github/SECURITY.md) for instructions on how to report them responsibly.