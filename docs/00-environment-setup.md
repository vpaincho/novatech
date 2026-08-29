# Environment Setup

## Objective

Prepare the local development environment for the NovaTech project.

## Hardware

- MacBook Pro
- Apple Silicon architecture (`arm64`)
- 24 GB RAM
- macOS 26.6

## Tools

### Homebrew

Homebrew is the package manager used to install and manage development tools on macOS.

Installation path:

```text
/opt/homebrew

Verification:

brew --version
which brew

Expected path:

/opt/homebrew/bin/brew

Git

Git was already installed on the system.

Verification:

git --version

Installed version:

git version 2.50.1
Python

The system originally resolved:

/usr/bin/python3

with Python 3.9.6.

A newer Python version was installed using Homebrew.

Verification:

python3 --version
which python3
pip3 --version

Final configuration:

Python 3.14.7
/opt/homebrew/bin/python3
/opt/homebrew/bin/pip3
PATH

The PATH environment variable determines where the shell searches for executable programs.

Verification:

echo $PATH

Homebrew appears before system paths, allowing Homebrew-managed tools to take priority.

Key Concepts Learned
Shell
PATH
Executables
Symbolic links
Package managers
Command resolution
Python versions

```text




