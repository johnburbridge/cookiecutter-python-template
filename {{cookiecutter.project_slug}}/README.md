# {{ cookiecutter.project_name }}

[![Python Version: {{ cookiecutter.python_version }}](https://badgen.net/badge/python/{{ cookiecutter.python_version }}/blue)](https://docs.python.org/{{
cookiecutter.python_version }}/)
[![Code Style: Black](https://badgen.net/badge/code%20style/black/black)](https://github.com/ambv/black)
[![pre-commit enabled][pre-commit badge]][pre-commit project]

[pre-commit badge]: https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white
[pre-commit project]: https://pre-commit.com/
## Installation

The Makefile can be used to initialise the project. This will install the requirement and install the githooks.

```bash
make init
```

## Documentation

Sphinx documentation generation is included. Google docstrings formatting is enabled as well as the "Read the Docs"
theme.

```bash
make docs
```

## Testing

```bash
make test
make clean
```
<!-- github-only -->