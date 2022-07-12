.PHONY: init
init:
	pip install -r requirements.txt
	git init
	pre-commit install

ifeq ($(OS),Windows_NT)
    RM = del /Q /F
    RRM = rmdir /Q /S
    mkdirp = mkdir $(subst /,\,$1)
    OPN = cmd /c start
else
    RM = rm -f
    RRM = rm -rf
    mkdirp = mkdir -p $1
    OPN = open
endif

.PHONY: clean
clean:
	-$(RRM) .pytest_cache
	-$(RRM) htmlcov
	-$(RRM) .mypy_cache
	-$(RM) .coverage
	-$(RRM) "docs/_build"


.PHONY: test
test:
	python -m pytest

.PHONY: htmlcov
htmlcov:
	python -m pytest --cov {{ cookiecutter.package_name }} --cov-report html
	-$(OPN) htmlcov/index.html

.PHONY: requirements
requirements:
	pip freeze > requirements.txt

.PHONY: lint
lint:
	flake8 {{ cookiecutter.package_name }} tests

.PHONY: format
format:
	mypy {{ cookiecutter.package_name }}
	black {{ cookiecutter.package_name }} tests

.PHONY: check
check:
	flake8 {{ cookiecutter.package_name }} tests
	mypy {{ cookiecutter.package_name }}

.PHONY: docs
docs:
	sphinx-apidoc -o docs {{ cookiecutter.package_name }}
	sphinx-build -b html docs docs/_build

.PHONY: open-docs
open-docs:
	-$(OPN) docs/_build/index.html