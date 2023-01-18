[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)

# 🐍 Python template project with linter, formatter and pre-commit

## 🔎 Overview

Use this template repository for fast Python developement setup

## 🛠️ Included tools

-   [Poetry](https://python-poetry.org/) for dependency managament
-   [Pre-commit](https://pre-commit.com/) for code consistancy and quality
-   [Editorconfig](https://editorconfig.org/) for compatible code editor configuration

## 📝 Visual Studio Code

This repository includes `.vscode` workspace configuration for Python language, linter, formatter and editor customization

## ✅ Linter and Formatter

This repository includes `flake8`, `black` and `isort` tools to maintain code consistency and quality. These tools together with VSCode configuration helps code quality while developing but they will run on commit and on pull request on GitHub.

The configuration file for these tools are:

-   `.flake8` for flake8 linter
-   `pyproject.toml` for black and isort formatter
    -   `[tool.black]` for black configuration
    -   `[tool.isort]` for isort configuration, uses black as profile

## 🤖 Pre-commit

This reposity includes pre-commit that runs on commit and have the following repo hooks:

-   `pre-commit-hooks` some built-in hooks
-   `poetry`
    -   `poetry-check` to check if poetry configuration is not broken
    -   `poetry-lock` to make sure `poetry.lock` file is up-to-date
    -   `poetry-export` to export installed packages to `dev-requirements.txt` for the ones installed with `poetry install --group dev` and to `requirements.txt` to include main packages, excluding the `dev`
-   `local` for local hooks using the same configuration used in the `Linter and Formatter` section
    -   `black` to check code formatting and show diff on FAIL and again to auto-format the code based on the `pyproject.toml` configuration
    -   `isort` to sort imports, using `black` as profile
    -   `flake8` to code lint and style checks using `.flake8` file

## 🎓 How-to use this template

Follow these steps to create a new repository using this template:

**TBD**
