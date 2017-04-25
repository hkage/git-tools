# git-tools

git-lost-commits will look for commits that were pushed to the git server but are potentially not part of any remote branch.

## Requirements

* Python 3
* Flake8
* git installed

## git hooks

### pre-commit-python

This is a git pre-commit hook, that will do some Python/Django specific validation checks:

* Flake8 checks for the changed files
* Check for Python debug statements (ipbd/pdb)
* Check for fuzzy translations in PO files

## git-lost-commits

### Usage

Simply type:

    $ ./git-lost-commits

and the result should look like this e.g.:

    b'2017-03-09 16:20:20'  b'4c7c37c'   b'Henning Kage'  b"Merge branch 'feature/abc' into development"...
    b'2017-03-09 14:59:43'  b'ebe9be0'   b'Henning Kage'  b"Merge branch 'feature/def' into 'feature/abc'"...
    b'2017-03-09 14:29:00'  b'2d2b740'   b'Henning Kage'  b"Merge branch 'development' into feature/abc"...
