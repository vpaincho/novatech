# Git and GitHub Setup

## Objective

Create a local Git repository for NovaTech and connect it to GitHub using SSH authentication.

## Repository Initialization

The project directory was initialized as a Git repository:

```bash
git init
Git stores its repository metadata inside:

.git/

Git Workflow

The basic Git workflow used was:

Working Directory
       ↓
   git add
       ↓
 Staging Area
       ↓
 git commit
       ↓
Repository History

The README file was added to the staging area:

git add README.md

The first commit was created:

git commit -m "Initial NovaTech project setup"
Git Identity

Git was configured with a global username and email:

git config --global user.name "Valentina Paincho"
git config --global user.email "<GitHub verified email>"
GitHub Remote

A GitHub repository called novatech was created.

The local repository was connected to GitHub through a remote named:

origin

Verification:

git remote -v
SSH Authentication

An ED25519 SSH key pair was generated:

ssh-keygen -t ed25519 -C "<GitHub verified email>"

Files created:

~/.ssh/id_ed25519
~/.ssh/id_ed25519.pub

The private key must never be shared.

The public key was added to GitHub.

Authentication was tested using:

ssh -T git@github.com

Successful authentication returned:

Hi vpaincho! You've successfully authenticated, but GitHub does not provide shell access.
Remote Configuration

The Git remote was changed from HTTPS to SSH:

git remote set-url origin git@github.com:vpaincho/novatech.git
First Push

The local main branch was pushed to GitHub:

git push -u origin main

The local branch now tracks:

origin/main

Verification:

git branch -vv
Current Workflow

Future changes can follow this workflow:

git add .
git commit -m "Describe the change"
git push
Key Concepts Learned
Repository
Commit
Staging area
Branch
HEAD
Remote
Origin
Push
SSH
Public/private key authentication

Guardás igual:

`Ctrl + O` → `Enter` → `Ctrl + X`

---

### 3. Troubleshooting

Ahora:

```bash
nano docs/troubleshooting.md

Pegá:

# Troubleshooting Log

This document records technical problems encountered during the NovaTech project and how they were diagnosed and resolved.

---

## Python command resolving to system Python

### Symptom

Running:

```bash
python3 --version

returned:

Python 3.9.6

and:

which python3

returned:

/usr/bin/python3

even after installing Python with Homebrew.

Investigation

The Homebrew Python installation was verified with:

brew list python
brew info python

Python 3.14.7 was confirmed to exist at:

/opt/homebrew/bin/python3

The PATH was checked:

echo $PATH

Homebrew was correctly listed before /usr/bin.

Root Cause

The shell was still using a cached command location for python3.

Resolution

The shell command cache was cleared:

hash -r
Verification
which python3
python3 --version
which pip3
pip3 --version

Final result:

/opt/homebrew/bin/python3
Python 3.14.7
/opt/homebrew/bin/pip3
GitHub authentication requesting password
Symptom

GitHub authentication through HTTPS requested credentials.

Investigation

The repository remote was checked:

git remote -v

The remote was configured using HTTPS.

Resolution

SSH authentication was configured instead.

Steps:

ssh-keygen -t ed25519 -C "<GitHub verified email>"
ssh -T git@github.com
git remote set-url origin git@github.com:vpaincho/novatech.git
Verification
git remote -v

returned an SSH remote and:

ssh -T git@github.com

successfully authenticated the GitHub account.




