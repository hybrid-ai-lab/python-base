# Project template

This template should be used for every Python project in the lab. It uses:

- `uv` for dependency management.
- `ruff` for code formatting.
- `pyright` for type checking.
- Pre-commit hooks for automated validation.

## Pre-commit hooks

First, set up the [pre-commit hooks](https://pre-commit.com/):

```sh
pre-commit install
```

Upon the first commit, the hooks will be installed and run, to validate that
all changes are compatible with the requirements imposed by the configuration
defined in `.pre-commit-config.yaml`.

Some hooks output error message that require a manual change (e.g., linting
errors). Other hooks perform automated fixes. Either way, you need to re-run
the commit command:

```sh
git commit -m "My message"
```

### Code formatting

Among the pre-commit hooks, you will find one that runs
[`ruff`](https://docs.astral.sh/ruff/) on every Python file. It is also warmly
recommended that you set up `ruff` in your IDE (e.g., Visual Studio Code, PyCharm).

### Typing

We recommend the use of [type hints](https://docs.python.org/3/library/typing.html)
of your code. One of the pre-commit hooks is [`pyright`](https://github.com/microsoft/pyright),
which will perform type checking when hints are available. This reduces greatly the
risk of bugs and the maintainability of the code.

## Dependency mangement

We use [`uv`](https://docs.astral.sh/uv/) for dependency management. It is as
full-featured and much faster than `poetry`.

1. Update the name of the project in `pyproject.toml`.
2. Add the dependencies you need (and run this same command every time you need
   a new package):

   ```sh
   uv add polars lightgbm
   ```

3. Take a look at the `uv`'s [Getting started guide](https://docs.astral.sh/uv/getting-started/).
