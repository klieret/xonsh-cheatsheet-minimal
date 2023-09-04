# Minimal xonsh cheat sheet

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/klieret/xonsh-cheatsheet-minimal/main.svg)](https://results.pre-commit.ci/latest/github/klieret/xonsh-cheatsheet-minimal/main)
[![Check Markdown links](https://github.com/klieret/xonsh-cheatsheet-minimal/actions/workflows/check-links.yaml/badge.svg)](https://github.com/klieret/xonsh-cheatsheet-minimal/actions/workflows/check-links.yaml)

Cheat sheet for [xonsh][].
For a longer cheat sheet, take a look at [anki-code's version](https://github.com/anki-code/xonsh-cheatsheet)

[xonsh]: https://xon.sh/

## Useful links

* [Official tutorial](https://xon.sh/tutorial.html)
* [Longer cheat sheet](https://github.com/anki-code/xonsh-cheatsheet)

## Basics

Sorted by probability of use.

* Evaluate python in bash command: `@(python_var)`, `@(1+1)`
* Capture output of bash command as string: `$(ls)`
    * Same but silent: `$[ls]`
* Environment variables:
    * Environment variable: `$HOME`
    * All environment variables: `${...}`
    * Environment variable from python expression: `${'HO'+'ME'}`
* Run bash command and return `CommandPipeline` object: `!(ls)`
    * Same but silent: `![ls]`
* Globbing: ``g`a*b*` `` lists all filenames (`str`) that match `a*b*` in the working directory
* Using [`pathlib`][pathlib]:
    * `p"/this/is/a/path/"` is a `Path`
    * Globbing: `` p`*.pt` `` retuns list of `Path`s

## Scripting

* Settings:
    * `$XONSH_SHOW_TRACEBACK = True`: Show verbose traceback
    * `$RAISE_SUBPROC_ERROR = True`: Raise error if subprocess fails (e.g., `$(doesntexist)`)
* Command line arguments:
    * Command line argument: `$ARG<n>` (e.g., `$ARG1`)
    * All arguments as python list: `$ARGS`

[pathlib]: https://docs.python.org/3/library/pathlib.html
