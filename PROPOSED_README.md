# SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT DIRECTIVES

## 1. IDENTITY & PRIME DIRECTIVE
**Role:** You are a Senior Principal Software Architect and Master Technical Copywriter with **40+ years of elite industry experience**. You operate with absolute precision, enforcing FAANG-level standards and the wisdom of "Managing the Unmanageable."
**Context:** Current Date is **December 2025**. You are building for the 2026 standard.
**Output Standard:** Deliver **EXECUTION-ONLY** results. No plans, no "reporting"—only executed code, updated docs, and applied fixes.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

---

## 2. INPUT PROCESSING & COGNITION
*   **SPEECH-TO-TEXT INTERPRETATION PROTOCOL:**
    *   **Context:** User inputs may contain phonetic errors (homophones, typos).
    *   **Semantic Correction:** **STRICTLY FORBIDDEN** from executing literal typos. You must **INFER** technical intent based on the project context.
    *   **Logic Anchor:** Treat the `README.md` as the **Single Source of Truth (SSOT)**.
*   **MANDATORY MCP INSTRUMENTATION:**
    *   **No Guessing:** Do not hallucinate APIs. You are anchored to the provided context.
    *   **Research First:** Assume access to **December 2025 Industry Standards** and **Security Threat Intelligence**.
    *   **Validation:** Assume access to internal verification tools (`docfork`) to validate every contract.
    *   **Reasoning:** Engage internal reasoning engines (`clear-thought-two`) to architect complex flows *before* writing code.

---

## 3. CONTEXT-AWARE APEX TECH STACKS (LATE 2025 STANDARDS)
**Directives:** This repository, `FilmFetch-Automated-Movie-Indexer-Service`, is confirmed as a **Python-based Media Automation Backend**. The Apex Toolchain for this profile is mandated.

*   **PRIMARY SCENARIO: DATA / SCRIPTS / AI (Python)**
    *   **Stack:** This project leverages **Python 3.12+**. Key tools include **uv** (for package management and dependency resolution), **Ruff** (for ultra-fast linting and formatting, configured for strict adherence), and **Pytest** (for robust unit and integration testing, especially for external API mocks).
    *   **Architecture:** Adheres to a **Modular Monolith** pattern, structured around distinct domains: `Discovery`, `Indexing`, `Acquisition`, and `ClientInterface`. This ensures clear separation of concerns for media workflow automation.
    *   **Data/Acquisition:** Integrates with external providers (Usenet/Torrent Trackers) via **adapter patterns** (Ports and Adapters principles applied to I/O layers).
    *   **CLI Framework:** Uses `Typer` for a modern, async-capable, and powerful command-line interface for management and orchestration.

---

## 4. DEVELOPMENT & VERIFICATION STANDARDS

**Architectural Principles Enforced:**
1.  **SOLID:** Strict adherence to Single Responsibility and Dependency Inversion.
2.  **DRY:** Avoid redundancy in parsing and authentication logic.
3.  **YAGNI:** Only implement features explicitly required by the indexing workflow; avoid speculative generalization.

**Verification Commands (Local Environment):**
bash
# 1. Resolve Dependencies (using uv)
uv sync

# 2. Format and Lint Codebase (using Ruff)
ruff check . --fix

# 3. Run Unit and Integration Tests (using Pytest)
pytest

# 4. Run Static Analysis against main application entry points
python -m mypy --strict


---

## 5. ARCHITECTURE DIAGRAM (Conceptual Flow)

mermaid
graph TD
    A[Watchlist / User Input] --> B{Discovery Engine (TMDB/Trakt)};
    B -- Metadata Candidates --> C[Indexing Resolver];
    C -- Resolved Item --> D[Acquisition Adapter Layer];
    D -- NZB/Magnet Link Request --> E[External Client (e.g., Sabnzbd/qBittorrent)];
    E -- Download Completion Signal --> F[Post-Processing & Library Merge];
    F --> G[Curated Media Library];
    style D fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#ccf,stroke:#333,stroke-width:2px


---

## 6. PROJECT STATUS AND CONTACT

<p align="center">
    <a href="https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/actions/workflows/ci.yml">
        <img src="https://img.shields.io/github/actions/workflow/status/chirag127/FilmFetch-Automated-Movie-Indexer-Service/ci.yml?label=Build&style=flat-square&logo=github" alt="Build Status">
    </a>
    <a href="https://codecov.io/gh/chirag127/FilmFetch-Automated-Movie-Indexer-Service">
        <img src="https://img.shields.io/codecov/c/github/chirag127/FilmFetch-Automated-Movie-Indexer-Service?label=Coverage&style=flat-square&logo=codecov" alt="Code Coverage">
    </a>
    <a href="#tech-stack">
        <img src="https://img.shields.io/badge/Python-3.12%2B-blue?style=flat-square&logo=python" alt="Language">
    </a>
    <a href="#tech-stack">
        <img src="https://img.shields.io/badge/Linter%2FFormatter-Ruff-brightgreen?style=flat-square&logo=ruff" alt="Linter">
    </a>
    <a href="https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service/blob/main/LICENSE">
        <img src="https://img.shields.io/badge/License-CC%20BY--NC%204.0-orange?style=flat-square" alt="License">
    </a>
    <a href="https://visitor-badge.glitch.me/badge?page_id=chirag127.FilmFetch-Automated-Movie-Indexer-Service">
        <img src="https://visitor-badge.glitch.me/badge?page_id=chirag127.FilmFetch-Automated-Movie-Indexer-Service&style=flat-square" alt="Visitors">
    </a>
</p>

## 🚀 Project Vision
FilmFetch is the next-generation, highly automated media acquisition engine designed to manage and synchronize diverse movie libraries using modern Usenet and Torrent protocols. It enforces strict dependency management via **uv** and utilizes **Typer** for a sophisticated, scalable command-line interface, ensuring robust and reliable content indexing.

<p align="center">
    <a href="https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service">⭐ Star this Repo</a>
</p>

---

<details>
<summary>🤖 AI AGENT DIRECTIVES (APEX_AGENT_CORE_V2026)</summary>

### 1. TECH STACK DEFINITION
*   **Language:** Python 3.12+
*   **Ecosystem:** `uv` (Package Management), `Ruff` (Linting/Formatting), `Pytest` (Testing).
*   **Architecture:** Modular Monolith / Ports & Adapters (I/O layers).
*   **CLI:** `Typer`.

### 2. ARCHITECTURAL GOVERNANCE
*   **IMPERATIVE:** All new code MUST be compliant with **Ruff's highly strict configuration** (equivalent to `Ruff+` standard). Failure to pass linting results in CI failure.
*   **DATA CONTRACTS:** External API interactions (e.g., Tracker APIs, Indexer APIs) MUST use explicit `pydantic` models for request/response validation, treating external data as inherently untrusted.
*   **MOCKING STRATEGY:** Integration tests involving I/O (download client signals, external API calls) MUST utilize **`pytest-mock`** to enforce clean isolation. All external HTTP/API calls must be mocked against fixture responses.

### 3. VERIFICATION COMMANDS (Agent Execution Context)
bash
# Execute all tests configured for the Acquisition module, mocking I/O.
pytest tests/acquisition/

# Perform a full static type check across the entire codebase.
python -m mypy --strict --ignore-missing-imports --check-untyped-defs .


</details>

---

## 📚 Table of Contents
1.  [Project Vision](#-project-vision)
2.  [AI Agent Directives](#-ai-agent-directives-apex_agent_core_v2026)
3.  [Tech Stack](#tech-stack)
4.  [Development Workflow](#development-workflow)
5.  [Contributing](#contributing)
6.  [License](#license)

---

## 🛠️ Tech Stack
This repository adheres to the **Apex Python Toolchain (2026 Standard)** for maximum velocity and maintainability.

| Domain | Technology | Version Standard |
| :--- | :--- | :--- |
| Language | Python | 3.12+ |
| Dependency Management | uv | Latest Stable |
| Linting/Formatting | Ruff | Strict |
| Testing Framework | Pytest | Integrated |
| CLI Library | Typer | Modern |
| Schema Validation | Pydantic | V2+ |

---

## 🚀 Development Workflow

### Prerequisites
Ensure Python 3.12+ is installed.

### Setup Guide
1.  **Clone Repository:**
    bash
    git clone https://github.com/chirag127/FilmFetch-Automated-Movie-Indexer-Service.git
    cd FilmFetch-Automated-Movie-Indexer-Service
    
2.  **Environment Resolution (using uv):**
    *Note: uv handles both dependency resolution and virtual environment creation automatically.*
    bash
    uv sync  # Installs all dependencies defined in pyproject.toml
    
3.  **Configuration:**
    Create a `.env` file in the root directory for sensitive credentials (API keys, client URLs). See `config/settings.example.env` for structure.

### Execution Scripts
| Command | Description |
| :--- | :--- |
| `python src/main.py index --source watchlist` | Runs the core indexing and acquisition cycle. |
| `python src/main.py verify --client torrent` | Checks connection health of configured download clients. |
| `ruff check .` | Runs static analysis and linting checks. |

---

## 🤝 Contributing
Contributions are welcome. Please adhere strictly to the Apex Principles outlined in the **`CONTRIBUTING.md`** file. All pull requests must pass CI checks, which enforce code coverage above 85% and zero linter warnings.

## ⚖️ License
This project is licensed under the **CC BY-NC 4.0 International License**. See the `LICENSE` file for details.
