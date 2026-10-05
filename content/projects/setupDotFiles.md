---
title: "setup-dotFiles - setting up a fresh Arch Linux workstation"
date: 2025-06-02 
---

setup-dotFiles sets up a new Arch Linux workstation, one question at a time.
A new machine otherwise costs the same evening again: install the packages,
paste the same `.bashrc`, generate an SSH key, join the `docker` group, and
try to remember what else there was. This is that evening written down once.

## Branches

The `arch` branch is Arch only. Everything installs with pacman and yay, and
there is no apt code path on it — nothing here will run on a Debian-family
system. The Debian and Ubuntu versions live on `master`, `bookworm`,
`bullseye`, `ubuntu2004`, `ubuntu2204` and `ubuntu2404`.

## What it does

- Installs the base packages from plain text lists, with pacman and yay.
- Configures git globals, tmux, bashrc and fzf.
- Sets up docker and group membership.
- Sets up a RAM disk.
- Ships a Containerfile, so the whole run can be tested in a throwaway
  container before it touches a real machine.
- Includes VPN DNS helpers and git hook templates.

The package lists and configuration are plain files, so changing what gets
installed does not mean reading the script.

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
| `pacman-apps.txt` | packages to install with pacman |
| `yay-apps.txt` | packages to install with yay |
| `fzf.bash` | fzf configuration |

Plus the utility scripts and hook templates.

## Licence

GNU GPL v3.0 or later. Source:
[setup-DotFiles](https://github.com/FPGArtktic/setup-DotFiles).
