---
title: "mtsh - a zsh prompt for multi-user and multi-repository work"
date: 2025-11-29
---

mtsh is an Oh My Zsh theme. It reports the state you would otherwise have to
ask for — the clock, the machine, where you are, and what git thinks of it —
and it draws one frame per command without making you wait for it.

It exists because switching between repositories on several machines means
losing track of three things at once: whether the working tree is clean,
whether it is in step with the remote, and what the machine is doing. Running
`git status`, `git fetch` and `free -h` by hand to find out is slower than
printing the answers.

## What the prompt reports

### The machine

| Field | Meaning |
|---|---|
| Date and time | Local clock at the moment the prompt was drawn |
| IP address | Current IPv4 address |
| CPU usage | Processor utilisation, from a `top` snapshot |
| RAM usage | Used against total |
| Logged users | Number of distinct users on the machine |
| Command timing | Wall-clock duration of the previous command |

The CPU and memory reads are non-blocking. A prompt that stalls is worse than
a prompt that tells you less.

### Git

| Field | Meaning |
|---|---|
| Branch | Current branch name and short commit hash |
| Working tree | Clean or dirty, colour-coded |
| Sync | Commits ahead of and behind the remote |
| Staleness | Marks the remote refs as old when they are over two minutes out of date |

The staleness marker is the point of the git section. `git status` reports
ahead/behind against whatever the last `git fetch` left behind, which on a
machine you have not pulled on today is a lie. The prompt says so rather than
repeating it.

### Layout

Paths are abbreviated when they get long. The frame is 70 characters, so the
line wraps the same way on every terminal it is likely to meet. Colours assume
a dark background.

## Status indicators

| Symbol | Meaning |
|---|---|
| CLEAN | No uncommitted changes |
| DIRTY | Uncommitted changes present |
| ✔ synced | Up to date with the remote |
| ⇡3 ahead | Three commits ahead of the remote |
| ⇣2 behind | Two commits behind the remote |
| ⇣1 ⇡2 | Diverged: behind and ahead at once |
| ⚠ no remote | No remote branch configured |
| ⚡ | Remote refs older than two minutes; ahead/behind may be wrong |

## Requirements

- zsh 5.0 or newer
- Oh My Zsh
- A Powerline font, for the frame and the symbols above

Installing a Powerline font:

```sh
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts
```

## Installation

```sh
git clone https://github.com/FPGArtktic/ohmyzsh-mtsh-theme.git
cp ohmyzsh-mtsh-theme/mtsh.zsh-theme ~/.oh-my-zsh/custom/themes/
sed -i 's/ZSH_THEME=".*"/ZSH_THEME="mtsh"/' ~/.zshrc
source ~/.zshrc
```

By hand, if you would rather see what changes: copy `mtsh.zsh-theme` into
`~/.oh-my-zsh/custom/themes/`, set `ZSH_THEME="mtsh"` in `~/.zshrc`, and start
a new shell.

## Colours

256-colour palette, chosen for dark backgrounds.

| Element | Colour |
|---|---|
| Date and time | Bright blue (117) |
| Directory | Bright yellow (228) |
| Git branch | Bright magenta (213) |
| Git clean | Bright green (121) |
| Git dirty | Bright red (210) |
| Git behind | Red (210) |
| Git ahead | Green (121) |
| IP address | Bright magenta (213) |
| CPU usage | Bright cyan (159) |
| RAM usage | Bright green (121) |
| Logged users | Orange (208) |

To change them, edit the colour variables at the top of `precmd_mtsh()`:

```sh
local C_BLUE='%F{117}'
local C_MAGENTA='%F{213}'
```

## Contributing

Patches are welcome. For anything larger than a fix, open an issue first and
say what you intend to change — it is cheaper to disagree about a plan than
about a branch.

## Licence

GNU General Public License v3.0. See the `LICENSE` file in the repository.

## Author

Mateusz Okulanis — [FPGArtktic@outlook.com](mailto:FPGArtktic@outlook.com).
Source: [ohmyzsh-mtsh-theme](https://github.com/FPGArtktic/ohmyzsh-mtsh-theme).

Developed on Arch Linux. I use arch btw.
