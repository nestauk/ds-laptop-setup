# ds-laptop-setup

ds-laptop-setup is a script to setup a macOS laptop for Nesta's data science workflows. It installs the softwares described in the new starters [laptop setup guide](https://docs.google.com/document/d/1ctvwW5iQ237pZlPAU_7xkJ33TkeeEQ4WGpE26W6qbUA/edit?tab=t.0#heading=h.2phzpxz6il91).

The script can be run multiple times, with any existing installations skipped or upgraded, without encountering any errors.

## Requirements

The script has been tested on macOS Sequoia (15.x) on Apple Silicon, but should run on Intel chips and older versions of macOS. Further testing will be implemented as necessary. Please file a bug report as an issue if you come across any errors.

Installation requires admin rights. For Nesta colleagues, please request admin permissions via the #ask-tech-nesta Slack channel.

## Install

Download, review, and execute the script:

```shell
curl --remote-name https://raw.githubusercontent.com/nestauk/ds-laptop-setup/dev/mac
less mac
sh mac 2>&1 | tee ~/laptop.log
```

Run with admin rights. You may be prompted to enter your password during the installation process, and select to install optional dependencies when the prompts appear. 

## Debugging

If you encounter any errors, review the log:

```shell
less ~/laptop.log
```

Then submit an [issue](https://github.com/nestauk/ds-laptop-setup/issues/new).

## What it sets up

Command-line tools (Python):

- [uv](https://docs.astral.sh/uv/), another Python package manager and installer (all-in-one!) 
- [pyenv](https://github.com/pyenv/pyenv) Python version manager
- [pyenv-virtualenv](https://github.com/pyenv/pyenv-virtualenv), pyenv plugin to manage Python versions within virtual environments
- [poetry](https://python-poetry.org/), yet another Python package manager
- [miniconda](https://docs.anaconda.com/miniconda/) **(optional)**, system package manager that we mainly use for our Python environment setup
- [ruff](https://docs.astral.sh/ruff/) for Python formatting and linting

Command-line tools (Other):

- [git](https://git-scm.com/) for version control
- [awscli](https://aws.amazon.com/cli/) to interact with AWS from the command line
- [homebrew](https://brew.sh/) package manager for installing software on your machine
- [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/) tool to build projects from templates

Development tools:

- [Visual Studio Code](https://code.visualstudio.com/) code editor, command line interface, and helpful extensions for easier development
- [Docker](https://www.docker.com/) for containerized development
- [direnv](https://direnv.net/) to read environment variables from your directory

System setup:

- [iTerm2](https://iterm2.com/) terminal
- [zsh](https://www.zsh.org/) as your shell language
- [Xcode](https://developer.apple.com/xcode/) developer tools, prerequisite for other applications

## Testing

Test your changes by running the script on a fresh install of macOS. You can use the free and open source emulator [UTM](https://mac.getutm.app/).

Tip: Make a fresh virtual machine with the installation of macOS completed and your user created and first launch complete. Then duplicate that machine to test the script each time on a fresh install that's ready to go.

## About

This project derives from [thoughtbot/laptop](https://github.com/thoughtbot/laptop), with the approach and base script adapted to Nesta's data science development environment.