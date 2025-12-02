# FilmFetch-Automated-Movie-Indexer-Service

![Build Status](https://img.shields.io/github/actions/workflow/user/chirag127/FilmFetch-Automated-Movie-Indexer-Service/ci.yml?style=flat-square&logo=githubactions)
![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/FilmFetch-Automated-Movie-Indexer-Service?style=flat-square&logo=codecov)
![Python Version](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)
![Linting](https://img.shields.io/badge/Linting-Ruff-success?style=flat-square&logo=ruff)
![License](https://img.shields.io/github/license/chirag127/FilmFetch-Automated-Movie-Indexer-Service?style=flat-square&logo=license)
![GitHub Stars](https://img.shields.io/github/stars/chirag127/FilmFetch-Automated-Movie-Indexer-Service?style=flat-square&logo=github)

A robust Python-powered backend service for automating the discovery, indexing, and acquisition of movie content via Usenet and torrents.

This engine intelligently manages desired movie lists, integrates seamlessly with download clients, and ensures a perfectly curated media library with minimal manual intervention.

<p align="center">
  <a href="https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/stargazers">
    <img src="https://img.shields.io/github/stars/chirag127/FilmFetch-Automated-Movie-Indexer-Service?style=social" alt="GitHub Stars">
  </a>
</p>

## Table of Contents

*   [Features](#features)
*   [Architecture](#architecture)
*   [Getting Started](#getting-started)
*   [Development Setup](#development-setup)
*   [Project Structure](#project-structure)
*   [AI Agent Directives](#ai-agent-directives) 🤖
*   [Contributing](#contributing)
*   [License](#license)

## Features

*   **Automated Content Discovery:** Scans Usenet (via NZB indexers) and torrent sites for specified movie titles.
*   **Intelligent Indexing:** Processes download results, filters based on user-defined quality, resolution, and release group preferences.
*   **Download Client Integration:** Seamlessly sends download tasks to popular clients (e.g., SABnzbd, qBittorrent, Transmission).
*   **Media Library Management:** Tracks downloaded content, checks for completeness, and can trigger post-download actions.
*   **Wishlist Management:** Allows users to maintain a list of desired movies for automated acquisition.
*   **Configurable Workflow:** Highly customizable settings for indexing, filtering, and download client parameters.

## Architecture

This project employs a **Modular Monolith** architecture, ensuring a cohesive yet maintainable codebase. Key components interact through well-defined interfaces, promoting separation of concerns.

mermaid
graph TD
    A[User Input/API] --> B(CLI Interface)
    B --> C{Core Logic Orchestrator}
    C --> D(Movie Discovery Engine)
    D --> E[Usenet/Torrent Sources]
    D --> F(Indexing & Filtering)
    F --> G{Download Client Manager}
    G --> H[Download Clients]
    G --> I(Media Library Tracker)
    I --> J(User Wishlist)
    C --> K(Configuration Manager)
    C --> L(Logger)
    E -- Content Data --> D
    H -- Downloaded Content --> I


## Getting Started

### Prerequisites

*   **Python:** Version 3.10 or higher is required.
*   **uv:** (Recommended for dependency management) - [Installation Guide](https://uv-rs.com/guides/installation/)
*   **Configuration:** A `config.yaml` file is necessary for setting up sources, download clients, and preferences.

### Installation (Using uv)

1.  **Clone the repository:**
    bash
    git clone https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service.git
    cd FilmFetch-Automated-Movie-Indexer-Service
    

2.  **Create and activate a virtual environment (optional but recommended):**
    bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
    

3.  **Install dependencies using uv:**
    bash
    uv pip install --sync --upgrade .[all]
    

## Development Setup

This project is built with Python 3.10+ and utilizes **uv** for package management, **Ruff** for linting/formatting, and **Pytest** for testing.

### Linting and Formatting

Ensure code quality and consistency:

bash
# Format code
ruff format .

# Lint code
ruff check .


### Testing

Run the test suite to verify functionality:

bash
# Run all tests
pytest


### Running the Service

Once configured, you can start the main indexing process:

bash
# Example command (assuming config.yaml is set up)
python -m filmfetch.cli index --config config.yaml


## Project Structure


FilmFetch-Automated-Movie-Indexer-Service/
├── .github/
│   ├── FUNDING.yml
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── pull_request_template.md
│   ├── CONTRIBUTING.md
│   ├── pull_request_template.md
│   ├── SECURITY.md
│   └── workflows/
│       └── ci.yml
├── src/
│   └── filmfetch/
│       ├── __init__.py
│       ├── cli.py             # Command Line Interface entry point
│       ├── core/
│       │   ├── __init__.py
│       │   ├── orchestrator.py  # Main workflow logic
│       │   ├── config.py        # Configuration loading and validation
│       │   └── logger.py        # Logging setup
│       ├── providers/
│       │   ├── __init__.py
│       │   ├── base.py          # Base class for providers
│       │   ├── usenet.py        # Usenet (NZB) provider implementation
│       │   └── torrent.py       # Torrent provider implementation
│       ├── clients/
│       │   ├── __init__.py
│       │   ├── base.py          # Base class for download clients
│       │   ├── sabnzbd.py       # SABnzbd client integration
│       │   └── qbittorrent.py   # qBittorrent client integration
│       ├── models/
│       │   ├── __init__.py
│       │   ├── movie.py         # Movie data model
│       │   └── download.py      # Download task model
│       └── utils/
│           ├── __init__.py
│           └── filters.py     # Content filtering logic
├── tests/
│   ├── __init__.py
│   ├── core/
│   ├── providers/
│   └── clients/
├── .gitignore
├── AGENTS.md
├── badges.yml
├── LICENSE
├── pyproject.toml
├── README.md
└── requirements.txt


## AI Agent Directives 🤖

<details>
  <summary>View AI Agent Directives</summary>

### 1. Identity & Prime Directive

*   **Role:** Senior Principal Software Architect, Master Technical Copywriter, DevOps Strategist with 40+ years of elite industry experience.
*   **Context:** December 2025. Building for the 2026 standard. Maintain FAANG-level standards and "Managing the Unmanageable" principles.
*   **Output Standard:** **EXECUTION-ONLY**. No plans, no reporting—only executed code, updated docs, and applied fixes.
*   **Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

### 2. Input Processing & Cognition

*   **Speech-to-Text Interpretation:** Strictly forbidden from executing literal typos. Infer technical intent based on project context and the `README.md` (SSOT).
*   **Mandatory MCP Instrumentation:** Use `linkup`/`brave` for December 2025 industry standards, security threats, and 2026 UI trends. Use `docfork` to verify external API signatures. Engage `clear-thought-two` for complex flow architecture *before* coding.

### 3. Context-Aware Apex Tech Stacks (Late 2025 Standards)

*   **Project Type:** Python-based AI automation tool.
*   **Stack:** **Python 3.10+**. Utilize **uv** for package management, **Ruff** for linting/formatting, and **Pytest** for testing. Adhere to **Modular Monolith** architecture.
*   **AI Integration:** Deeply integrated with **Google Gemini API** (`gemini-3-pro` by default) for intelligent batch-processing and decision-making. Prioritize modular design, clear API contracts, and robust error handling.
*   **CLI Framework:** Use `Click` or similar for a powerful and intuitive command-line interface.

### 4. Apex Naming Convention (*Star Velocity* Engine)

*   **Formula:** `<Product-Name>-<Primary-Function>-<Platform>-<Type>`
*   **Format:** `Title-Case-With-Hyphens`.
*   **Constraints:** 3 to 10 words, include high-volume keywords. NO numbers, emojis, underscores, or generic qualifiers without context.
*   **Example:** `FilmFetch-Automated-Movie-Indexer-Service`.

### 5. The README Replication Protocol

*   **Purpose:** README is the Project Operating System.
*   **Sections:** Visual Authority (Hero Banner, Badges), Structural Clarity (BLUF, Architecture, ToC), AI Agent Directives (collapsible), Development Standards (Setup, Scripts, Principles).

### 6. Development Principles

*   **SOLID:** Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion.
*   **DRY:** Don't Repeat Yourself.
*   **YAGNI:** You Ain't Gonna Need It.
*   **KISS:** Keep It Simple, Stupid.

### 7. Verification Commands

*   **Lint & Format:** `ruff check .` and `ruff format .`
*   **Test:** `pytest`
*   **Build:** `uv package .` (for potential packaging)
*   **Dependencies:** `uv sync --all-features`

### 8. Testing Strategy

*   **Unit Tests:** Cover individual functions and classes with mock dependencies.
*   **Integration Tests:** Verify interactions between components (e.g., Configuration -> Discovery -> Client).
*   **End-to-End Tests:** Simulate user workflows via the CLI.

### 9. Deployment Strategy

*   **CI/CD:** GitHub Actions (`.github/workflows/ci.yml`) for automated testing and linting on every push/PR.
*   **Packaging:** Pyproject.toml configured for build backend (e.g., Hatchling/setuptools) and dependency specification.
*   **Distribution:** Potential for distribution via PyPI or private repositories.

### 10. Security Mandate

*   **Dependency Scanning:** Regularly scan dependencies for vulnerabilities.
*   **Secrets Management:** Never hardcode secrets. Use environment variables or a dedicated secrets manager.
*   **API Security:** Validate all external API inputs and outputs. Implement rate limiting and proper authentication.
*   **Input Validation:** Sanitize and validate all user-provided input to prevent injection attacks.

### 11. Code Documentation

*   **Docstrings:** Adhere to a standard format (e.g., Google Style) for all functions, classes, and modules.
*   **Type Hinting:** Utilize Python's type hinting extensively for improved readability and static analysis.

</details>

## Contributing

Contributions are welcome! Please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix (`git checkout -b feature/YourFeature` or `git checkout -b fix/YourBug`).
3.  Make your changes and ensure tests pass.
4.  Commit your changes (`git commit -m 'Add some YourFeature'`)
5.  Push to the branch (`git push origin feature/YourFeature`)
6.  Open a Pull Request.

Please adhere to the [CONTRIBUTING.md](/.github/CONTRIBUTING.md) guidelines.

## License

This project is licensed under the **CC BY-NC 4.0** license. See the [LICENSE](LICENSE) file for details.
