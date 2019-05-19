# Flake8 Markdown

[
![PyPI](https://img.shields.io/pypi/v/flake8-markdown.svg)
![PyPI](https://img.shields.io/pypi/pyversions/flake8-markdown.svg)
![PyPI](https://img.shields.io/pypi/l/flake8-markdown.svg)
](https://pypi.org/project/flake8-markdown/)
[![TravisCI](https://travis-ci.org/johnfraney/flake8-markdown.svg?branch=master)](https://travis-ci.org/johnfraney/flake8-markdown)

Flake8 Markdown lints [GitHub-style Python code blocks](https://help.github.com/en/articles/creating-and-highlighting-code-blocks#fenced-code-blocks) in Markdown files using [`flake8`](https://flake8.readthedocs.io/en/stable/).

This package helps improve a Python project's documentation by ensuring that code samples are error-free.

## Usage

### CLI

You can use Flake8 Markdown as a CLI tool using the `flake8-markdown` command.

`flake8-markdown` accepts one or more [globs](https://docs.python.org/3.7/library/glob.html) as its arguments.

Example:

```console
$ flake8-markdown flake8-markdown "tests/samples/*.md"
tests/samples/emphasized_lines.md:6:1: F821 undefined name 'emphasized_imaginary_function'
tests/samples/basic.md:8:48: E999 SyntaxError: EOL while scanning string literal
tests/samples/basic.md:14:7: F821 undefined name 'undefined_variable'
```

### pre-commit hook

You can also add `flake8-markdown` to your project using [pre-commit](https://pre-commit.com/). When configured, any staged Markdown files will be linted using `flake8-markdown` once you run `git commit`.

To enable this hook in your local repository, add the following `repo` to your `.pre-commit-config.yaml` file:

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/johnfraney/flake8-markdown
    rev: latest
    hooks:
      - id: flake8-markdown
```

## History

### [0.1.0] - 2019-05-19

#### Added

- Added code for initial release
