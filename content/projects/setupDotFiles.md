---
title: "setup-dotFiles - My personal dotfiles and configuration scripts for Ubuntu 24.04"
date: 2025-06-02 
---

Dotfiles and setup scripts for a fresh Ubuntu 24.04 or Arch Linux machine (I
use arch, btw). It installs the packages, writes the configuration and sets up
the storage I want before I start working, rather than over the following week
as I notice each thing missing.

## What it does

- Installs the base packages: git, build-essential, curl and the rest.
- Configures git globals, tmux, bashrc and fzf.
- Ships a Dockerfile, so the whole setup can be tested in a throwaway Ubuntu
  24.04 container before it touches a real machine.
- Sets up a RAM disk.
- Keeps its package lists and configuration in plain text files, so changing
  what it installs does not mean reading the script.
- Includes VPN DNS helpers and git hook templates.

## Usage

```sh
./setup-dotFiles.sh                 # run it
./setup-dotFiles.sh --dry-run       # report, change nothing
./setup-dotFiles.sh -v              # verbose
./setup-dotFiles.sh -y              # assume yes
```

## Components

| File | Purpose |
|---|---|
| `bashrc` | bash configuration |
| `tmux.conf` | tmux configuration |
| `apt-apps.txt` | packages to install with apt |
| `yay-apps.txt` | packages to install with yay |
| `fzf.bash` | fzf configuration |

Plus the utility scripts and hook templates.

## Licence

GNU GPL v3.0. Source:
[setup-DotFiles](https://github.com/FPGArtktic/setup-DotFiles).
