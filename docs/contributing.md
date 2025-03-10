---
title: Contributing
---

# 🍪 Contributing
bigtree is a tree implementation package for Python. It integrates with Python lists, dictionaries, and pandas DataFrame.

Thank you for taking the time to contribute. Contributing to this package is an excellent opportunity to dive into tree implementations.

## Set Up

First, [fork the repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo) and clone the forked repository.

```console
$ git clone git@github.com:<your-username>/bigtree.git
```

Next, create a virtual environment and activate it.

```console
$ conda create -n bigtree_venv python=3.10
$ conda activate bigtree_venv
```

To check if it worked,

```console
$ which pip
/<some directory>/envs/bigtree_venv/bin/pip
```

From the project folder, install the required python packages locally in editable mode and set up pre-commit checks.

    $ python -m pip install -e ".[all]"
    $ python -m pip install pre-commit
    $ pre-commit install

## Developing

After making your changes, create a new branch, add and commit your changed files.
In this example, lets assume the changed file is `README.md`.
If there are any pre-commit changes and/or comments, do modify, re-add and re-commit your files.

```console
$ git checkout -b chore/update-readme
$ git add README.md
$ git commit -m "chore: updated README"
```

Push your changes to your created branch and [create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) from your fork.

```console
$ git push origin chore/update-readme
```

## Testing and Documentation

If there are changes related to code, please make sure that the <mark>unit tests pass</mark> and the
<mark>code coverage is 100%</mark>.

```console
$ python -m pip install pytest coverage
$ pytest --cov-report=term-missing --cov-config=pyproject.toml --cov=bigtree
```

Make sure your add/update the tests and documentations accordingly.

If there are changes to the docstrings and/or sample codes in the docstring, do run the following lines of code to
generate the <mark>coverage report and test report for docstrings</mark>.
Refer to the console log for information on the file location of the reports.

```console
$ python -m pip install hatch
$ hatch run docs:coverage
$ hatch run docs:doctest
```

## Convention and Standards

When creating branches, it is recommended to create them in the format `type/action`. For example,

```console
$ git checkout -b feat/add-this
```

During pre-commit checks, this project enforces [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) when writing commit messages, and checks and formats code using `black`, `flake8`, `isort`, and `mypy`.
- The regex for conventional commits is as such `(?s)(build|ci|docs|feat|fix|perf|refactor|style|test|chore|revert|bump)(\(\S+\))?!?:( [^\n\r]+)((\n\n.*)|(\s*))?$`.

For testing, this project uses `pytest` and `coverage` package for testing of codes, and `docstr-coverage` and `doctest` package for testing of docstrings.

## Consequent Changes

Please [open an issue](https://github.com/kayjan/bigtree/issues/new/choose) to discuss important changes before embarking on an implementation.
