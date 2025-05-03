# Contributing to PDS (Portable Data Store)

Thank you for considering contributing to PDS! We appreciate any help, whether it's reporting bugs, suggesting features, improving documentation, writing code, or adding tests. Your contributions are valuable to the project.

This document provides guidelines for contributing to ensure a smooth and effective process for everyone involved.

## Code of Conduct

Be a decent human being. That's it.

## How Can I Contribute?

* **Reporting Bugs:** If you find a bug, please check the existing [Issues](https://github.com/kiss-oliver/PDS/issues) first to see if it has already been reported. If not, please open a new issue.
* **Suggesting Enhancements:** Have an idea for a new feature or an improvement to an existing one? Check the [Issues](https://github.com/kiss-oliver/PDS/issues) to see if it's already being discussed. If not, open a new issue to suggest it.
* **Pull Requests:** If you want to contribute code or documentation fixes/improvements, please follow the process outlined below.

## Setting Up Your Development Environment

Feel free to use other package/environment managers, this is just our workflow. As long as your development environment matches, you should be good to go.

1.  **Fork & Clone:** Fork the repository on GitHub and then clone your fork locally:
    ```bash
    git clone https://github.com/YOUR_USERNAME/PDS.git
    cd PDS
    ```
2.  **Python Version:** Ensure you have the python version in `.python-version` installed. We recomment using pyenv.
3.  **Install `uv`:** If you don't have `uv` installed, follow the instructions [here](https://github.com/astral-sh/uv#installation).
4.  **Create Virtual Environment:** Use `uv` to create and activate a virtual environment:
    ```bash
    uv venv
    source .venv/bin/activate  # Linux/macOS
    # .venv\Scripts\activate  # Windows
    ```
5.  **Install Dependencies:** Use `uv` to install all dependencies, including development tools like `ruff`:
    ```bash
    uv sync --dev
    ```
    This command reads the `pyproject.toml` and `uv.lock` files to install the exact dependencies needed for development.

## Submitting Bug Reports

When reporting a bug, please include:

* Your operating system name and version.
* Your Python version.
* The version of the `python-pds` package you are using (if applicable).
* Clear steps to reproduce the bug.
* What you expected to happen.
* What actually happened (including full error messages/tracebacks if possible).

Please search existing issues before creating a new one.

## Suggesting Features

When suggesting a feature, please:

* Explain the problem you're trying to solve or the use case the feature would enable.
* Describe your proposed solution clearly.
* Explain why this feature would be valuable to PDS users.
* Check existing issues and discussions first.

## Pull Request Process

We welcome pull requests! Please follow these steps:

1.  **Fork & Branch:** Fork the repository and create a new branch from `main` for your changes. Use a descriptive branch name (e.g., `feat/add-checksum-option`, `fix/handle-empty-file`, `docs/update-readme`).
    ```bash
    git checkout -b feat/your-feature-name
    ```
2.  **Make Changes:** Write your code or documentation improvements.
3.  **Code Style & Linting:**
    * Ensure your code adheres to the project's style. We use [Ruff](https://github.com/astral-sh/ruff) for formatting and linting.
    * **Format your code:** Run `uv run ruff format .`
    * **Check for lint errors:** Run `uv run ruff check .`
    * These checks are enforced by the `lint-format.yml` GitHub Actions workflow. Please ensure it passes locally before pushing.
4.  **Testing:**
    * *(Current Status: Please note that PDS currently lacks a comprehensive automated test suite. We plan to rely on pytest. Contributions that add tests, especially for new features or bug fixes, are highly encouraged!)*
    * If tests exist for the area you are modifying, ensure they pass.
    * If you are adding a new feature or fixing a bug, please add corresponding tests.
    * Run tests using: `uv run pytest`.
5.  **Commit Messages:**
    * Your commit messages **must** follow the [Conventional Commits specification](https://www.conventionalcommits.org/en/v1.0.0/). This is enforced by our CI process.
    * The basic format is `<type>[optional scope]: <description>`.
    * Allowed types include: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
    * Example: `feat: add support for metadata encryption` or `fix(save): correct handling of zero-byte values`.
6.  **Documentation:** If your change affects user-facing behavior or adds new features, please update the `README.md` or relevant docstrings accordingly.
7.  **Push Changes:** Push your feature branch to your fork on GitHub.
    ```bash
    git push origin feat/your-feature-name
    ```
8.  **Open Pull Request:** Go to the original `kiss-oliver/PDS` repository on GitHub and open a pull request from your fork's branch to the `main` branch.
9.  **PR Title:** Your pull request title **must** also follow the Conventional Commits format (e.g., `feat: add new feature X`). This is checked by the `semantic-pr-check.yml` workflow.
10. **Code Review & CI:** Address any feedback from reviewers and ensure all CI checks (linting, formatting, semantic checks, tests) pass.

## Questions?

If you have questions about contributing, feel free to open an [Issue](https://github.com/kiss-oliver/PDS/issues) on GitHub.

Thank you again for your interest in contributing!