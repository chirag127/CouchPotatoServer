# FilmFetch: Media Acquisition Automation Backend


![FilmFetch Hero Banner](https://via.placeholder.com/1280x400.png?text=FilmFetch%20-%20Automated%20Media%20Acquisition)


<div align="center">

[
![Build Status](https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/actions/workflows/ci.yml/badge.svg?style=flat-square)
](https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/actions/workflows/ci.yml)
[
![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/FilmFetch-Media-Acquisition-Automation-Backend?style=flat-square&token=CODECOV_TOKEN_PLACEHOLDER)
](https://codecov.io/gh/chirag127/FilmFetch-Media-Acquisition-Automation-Backend)
[
![Tech Stack](https://img.shields.io/badge/tech-Python%20%7C%20uv%20%7C%20Ruff-blue?style=flat-square)
](https://github.com/astral-sh/uv)
[
![Linter](https://img.shields.io/badge/linter-Ruff-blueviolet?style=flat-square)
](https://github.com/astral-sh/ruff)
[
![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg?style=flat-square)
](https://creativecommons.org/licenses/by-nc/4.0/)
[
![GitHub Stars](https://img.shields.io/github/stars/chirag127/FilmFetch-Media-Acquisition-Automation-Backend?style=flat-square&logo=github)
](https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/stargazers)

</div>

> **BLUF:** FilmFetch is a high-performance, automated backend for intelligent media discovery, indexing, and acquisition. It seamlessly integrates with Usenet and torrent clients to manage your desired content, curate your media library, and ensure a robust, scalable workflow.

<div align="center">
  <a href="https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/stargazers"><strong>Star ⭐ this Repo</strong></a> to support its development!
</div>

---

## 🏛️ Architecture Overview

FilmFetch is designed as a **Modular Monolith**, promoting clean separation of concerns while maintaining ease of deployment. Each component operates independently, interacting through well-defined service layers.

sh
filmfetch/
├── api/                # External API clients (SABnzbd, qBittorrent, Prowlarr)
├── core/               # Business logic, scheduling, and core services
├── indexers/           # Logic for querying and parsing indexer results
├── models/             # Data models and schemas (Pydantic)
├── notification/       # Notification services (Discord, Telegram, etc.)
├── parsers/            # Advanced parsing for release names and metadata
├── cli.py              # Command-Line Interface entrypoint (Typer/Click)
└── config.py           # Centralized configuration management


---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🚀 Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [🔧 Configuration](#-configuration)
- [▶️ Usage](#️-usage)
- [🤖 AI Agent Directives](#-ai-agent-directives)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

---

## ✨ Features

- **Automated Content Discovery:** Monitors RSS feeds and performs scheduled searches for desired media.
- **Indexer Integration:** Natively supports Prowlarr and Jackett for unified indexer management.
- **Download Client Management:** Seamlessly sends content to SABnzbd (Usenet) and qBittorrent (Torrents).
- **Quality & Profile Management:** Define quality profiles to grab the specific releases you want.
- **Robust & Resilient:** Built-in retry logic and failure notifications.
- **Extensible Notification System:** Get updates via Discord, Telegram, and more.
- **Headless & Lightweight:** Designed to run efficiently on servers, NAS devices, or Docker containers.

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- [uv](https://github.com/astral-sh/uv) (for package management)
- Access to Usenet/torrent indexers and download clients.

### Installation

1.  **Clone the repository:**
    bash
    git clone https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend.git
    cd FilmFetch-Media-Acquisition-Automation-Backend
    

2.  **Install dependencies using `uv`:**
    bash
    uv sync
    

---

## 🔧 Configuration

1.  Rename `config.example.yml` to `config.yml`.
2.  Edit `config.yml` with your details for indexers, download clients, and media paths.
3.  Alternatively, FilmFetch can be configured using environment variables, which is ideal for Docker deployments. (e.g., `FILMFETCH_SABNZBD_API_KEY=your_key`).

---

## ▶️ Usage

FilmFetch is operated via its command-line interface.

- **Run a manual search for a specific movie:**
  bash
  uv run search movie "Dune Part Two 2024"
  

- **Add a new TV series to be monitored:**
  bash
  uv run add series "Shogun"
  

- **Start the scheduler to run automated tasks:**
  bash
  uv run start
  

---

## 🤖 AI Agent Directives

<details>
<summary><strong>SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)</strong></summary>

### 1. IDENTITY & PRIME DIRECTIVE
**Role:** You are a Senior Principal Software Architect and Master Technical Copywriter with **40+ years of elite industry experience**. You operate with absolute precision, enforcing FAANG-level standards.
**Context:** Current Date is **December 2025**. You are building for the 2026 standard.
**Output Standard:** Deliver **EXECUTION-ONLY** results. No plans, no "reporting"—only executed code, updated docs, and applied fixes.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

### 2. CONTEXT-AWARE APEX TECH STACKS (LATE 2025 STANDARDS)
**Directives:** This repository, `FilmFetch-Media-Acquisition-Automation-Backend`, is a Python-based backend automation system. You must adhere to the following stack and architectural principles.

-   **PRIMARY SCENARIO: PYTHON AUTOMATION BACKEND**
    -   **Package Management:** **uv** is the non-negotiable standard for dependency resolution and virtual environment management. All new dependencies must be added to `pyproject.toml`.
    -   **Linting & Formatting:** **Ruff** is the sole authority for code quality. Execute `uv run lint` and `uv run format` before every commit. The CI pipeline will reject non-compliant code.
    -   **Testing Framework:** **Pytest** is the standard for all unit, integration, and functional tests. New features require corresponding tests with a minimum of 85% coverage.
    -   **Architecture:** Adheres to a **Modular Monolith** pattern. Logic must be strictly separated into functional modules (e.g., `api`, `indexers`, `notification`). Avoid monoliths within modules. Use dependency injection for services.
    -   **API Integrations:** All external API clients (SABnzbd, qBittorrent, etc.) must use robust clients with error handling, timeouts, and retry logic. Prefer libraries that use modern `httpx` and `Pydantic`.
    -   **CLI Framework:** The primary user interface is a CLI built with `Typer` or `Click`. Commands must be intuitive, well-documented, and provide clear user feedback.

-   **DEVELOPMENT PRINCIPLES:**
    -   **SOLID:** Enforce Single Responsibility and Dependency Inversion principles rigorously.
    -   **DRY (Don't Repeat Yourself):** Abstract common logic into reusable functions and services.
    -   **YAGNI (You Ain't Gonna Need It):** Do not add features or complexity that are not required by a current, defined task.

### 3. VERIFICATION & EXECUTION COMMANDS
- **Verify Environment & Dependencies:** `uv sync`
- **Run Linters & Formatters:** `uv run lint && uv run format`
- **Run All Tests:** `uv run test`
- **Run with Coverage:** `uv run coverage`

</details>

---

## 🤝 Contributing

Contributions are welcome! Please read the [**CONTRIBUTING.md**](https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/blob/main/.github/CONTRIBUTING.md) guide for details on our code of conduct and the process for submitting pull requests.

---

## 📜 License

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License** - see the [**LICENSE**](https://github.com/chirag127/FilmFetch-Media-Acquisition-Automation-Backend/blob/main/LICENSE) file for details.
