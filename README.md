[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)

# 🐍 Python template project with linter, formatter and pre-commit

## 🔎 Overview

Use this template repository for fast Python development or test automation framework setup

## 🛠️ Included tools

-   [Poetry](https://python-poetry.org/) for dependency management
-   [Pre-commit](https://pre-commit.com/) for code consistency and quality
-   [Editorconfig](https://editorconfig.org/) for compatible code editor configuration

## 📝 Visual Studio Code

This repository includes `.vscode` workspace configuration for Python language, linter, formatter and editor customization

## ✅ Linter and Formatter

This repository includes `flake8`, `black` and `isort` tools to maintain code consistency and quality. These tools together with VSCode configuration helps code quality while developing but they will run on commit and on pull request on GitHub

The configuration file for these tools are:

-   `.flake8` for flake8 linter
-   `pyproject.toml` for black and isort formatter
    -   `[tool.black]` for black configuration
    -   `[tool.isort]` for isort configuration, uses black as profile

## 🤖 Pre-commit

This repository includes pre-commit that runs on commit and have the following repo hooks:

-   `pre-commit-hooks` some built-in hooks
-   `poetry`
    -   `poetry-check` to check if poetry configuration is not broken
    -   `poetry-lock` to make sure `poetry.lock` file is up-to-date
    -   `poetry-export` to export installed packages to `dev-requirements.txt` for the ones installed with `poetry install --group dev` and to `requirements.txt` to include main packages, excluding the `dev`
-   `local` for local hooks using the same configuration used in the `Linter and Formatter` section
    -   `black` to check code formatting and show diff on FAIL and again to auto-format the code based on the `pyproject.toml` configuration
    -   `isort` to sort imports, using `black` as profile
    -   `flake8` to code lint and style checks using `.flake8` file

## ⚙️ GitHub Action

This repository includes a GitHub Action workflow on `.github/workflows/ci.yaml` that runs the `pre-commit` on all files in the Pull Request

## 🎓 How-to use this template

Follow these steps to create a new repository using this template:

From this repository [URL](https://github.com/ltsuda/python-template-project), select `Use this template -> Create new repository`, type a `name` for your repository, choose the repository `visibility` and make sure to `check` **Include all branches** so you have access to other Python versions setup

After cloning the new repository, change to the corresponding branch of the Python version you want to use on your project. Rename or remove `src/template_project` directory and update section `[tool.poetry]` from `pyproject.toml` file and run the following commands to install project dependencies and pre-commit:

Make sure to have the corresponding Python version installed and to be in use in the current shell. As recommendation, use [Pyenv](https://github.com/pyenv/pyenv) to manage multiple Python versions

```bash
python-template-project ❯ poetry shell
python-template-project (template-project-py3.11) ❯ poetry update
python-template-project (template-project-py3.11) ❯ pre-commit install
```

If you don't want to use poetry, you can use the `[dev-]requirements.txt` files as they are synched with the poetry dependencies but then you have to control them yourself

**NOTE:**
-   You can remove any other branch you don't need
-   You can set the selected branch to be the `default`, remove the `main` branch and then rename the selected one to `main` or anything you desire

Reference:
-   https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository

## Available Python setup

From https://devguide.python.org/versions/

-   Python 3.7
-   Python 3.8
-   Python 3.9
-   Python 3.10
-   Python 3.11

As some of the tools available doesn't support anymore or are not available for `Python 3.6`, the branch setup will not be created in this template. If you really need it, feel free to use this template and configure it to `Python 3.6` as you wish, if possible
