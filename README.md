[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-black.json)](https://github.com/copier-org/copier)

# DAALAB - 🌱 Substrate

A minimal [Copier template](https://github.com/copier-org/copier) for scaffolding Python packages with a focus on code configuration.

## 🎁 Features

- 🌈 Cross-platform support for Linux, macOS, and Windows
- 🐚 Modern shell prompt with [Starship](https://github.com/starship/starship)
- 📦 Packaging and dependency management with [uv](https://github.com/astral-sh/uv)
- 🚚 Installing from and publishing to [PyPI](https://pypi.org/)
- ⚡️ Task running with [Poe the Poet](https://github.com/nat-n/poethepoet)
- 💅 Code formatting with [Ruff](https://github.com/charliermarsh/ruff)
- ✅ Code linting with [Pre-commit](https://pre-commit.com/), [Mypy](https://github.com/python/mypy), and [Ruff](https://github.com/charliermarsh/ruff)
- 🧪 Test coverage with [Coverage.py](https://github.com/nedbat/coveragepy)

## ✨ Using

> [!TIP]
> You should first [install uv](https://docs.astral.sh/uv/getting-started/installation/) to be able to run the commands below.

### Create a new Python project

To create a new Python project with this template, run:

```sh
uvx copier copy gh:superlinear-ai/substrate path/to/local/repository
```

### Update your Python project

To update your Python project to the latest template version, run:

```sh
uvx copier update --exclude src/ --exclude tests/
```

## 🍪 Migrating from Previous Versions

To migrate a project from a previous version of Substrate to this simplified version, follow these steps:

1. In your project repository, run:

    ```sh
    # Create a new branch
    git checkout -b rescaffold

    # Remove unnecessary files
    rm -rf .github .gitlab-ci.yml docs/ mkdocs.yml Dockerfile docker-compose.yml .devcontainer/
    
    # Rescaffold the project without changing src/ and tests/
    uvx copier copy --overwrite --exclude src/ --exclude tests/ gh:superlinear-ai/substrate .
    ```

2. Review the changes to `pyproject.toml` and reinsert your project's dependencies.
3. Review the changes to `README.md` and reinsert your project's documentation.
4. Commit and push all changes with:

    ```sh
    # Stage all changes
    git add .

    # Commit the staged changes
    git commit -m "build: upgrade scaffolding"

    # Push the committed changes
    git push origin rescaffold
    ```

5. Create a PR from your branch, review it, and merge it!

## Contributing

<details>
<summary>Prerequisites</summary>

1. [Install uv](https://docs.astral.sh/uv/getting-started/installation/).
1. _Optional:_ install a [Nerd Font](https://www.nerdfonts.com/font-downloads) such as [FiraCode Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode) and configure your editor to use it.

</details>

<details open>
<summary>Development environment setup</summary>

Clone this repository and run the following from root of the repository:

```sh
# Create and install a virtual environment
uv sync

# Activate the virtual environment
source .venv/bin/activate

# Install the pre-commit hooks
pre-commit install --install-hooks
```

</details>

<details open>
<summary>Developing</summary>

- Run `poe` to see available development tasks.
- Run `uv add {package}` to add new dependencies to the template's pyproject.toml.
- Run `uv sync --upgrade` to upgrade dependencies.

</details>
