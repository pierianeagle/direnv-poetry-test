# direnv-poetry-test

This is a test of direnv's workflow with poetry.

# When starting a new project:
```zsh
# initialise project
poetry new direnv-poetry-test

# create repo
git init

# create .gitignore
echo .direnv/ > .gitignore

# create .tool_versions
asdf local python latest

# create venv
echo "layout poetry" > .envrc
direnv allow

# install packages
poetry add pendulum

# export requirements
# poetry export -f requirements.txt --output requirements.txt
```

## When working on an existing project:
```zsh
# clone repo
git clone https://...

# install python
asdf install

# create venv
echo "layout poetry" > .envrc
direnv allow

# intialise project
poetry init

# install packages
poetry install

# make binaries accessible from PATH
asdf reshim python
```

# Poetry

To store virtual environments in the project's root directory:

```zsh
poetry config virtualenvs.in-project true
poetry config --list
```

For extra information in regards to this workflow and direnv configuration, see:

https://github.com/direnv/direnv/wiki/Python#poetry
