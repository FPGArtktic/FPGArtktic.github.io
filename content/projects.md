+++
title = "Projects"
date = "2025-06-02"
author = "Mateusz Okulanis"
+++

Things I have built and still use. Everything here is public, most of it is
GPL-3.0, and all of it exists because I wanted it on my own machine first.

{{< hr >}}

## Terminal tools

**hyprtilt** – a keyboard-first TUI and command line for arranging and
rotating [Hyprland](https://hypr.land) monitors. It edits your own
configuration in place inside a managed block, both the Lua form
(`hl.monitor({...})`) and hyprlang (`monitor=...`). One static Rust binary,
no daemon, no sidecar files.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/hyprtilt)

{{< hr >}}

**LazySubmodules** – Git submodules that track branches, tag patterns or
fixed commits instead of only a detached SHA. A scriptable command line and
an interactive TUI, with a lock file. Written in Go; `lsm` is the short name.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/lazysubmodules)

{{< hr >}}

**mtsh** – a zsh prompt that reports the state you would otherwise have to
ask for: the clock, the machine, where you are, and what git thinks of it.
One frame per command, and it does not make you wait for it.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/ohmyzsh-mtsh-theme)

[ <<< READ MORE >>> ](/projects/mtsh-theme/)

{{< hr >}}

## Local inference, local notes

Three projects that share one rule: nothing leaves the machine.

**SHUTTLE** – a local-inference layer for coding agents. Your files are read
by llama.cpp on your own hardware instead of being pushed into the agent's
context. MCP server, rootless Podman, no egress, cited answers, and every
number in the README measured rather than asserted.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/shuttle-stack)

{{< hr >}}

**glosator** – turns a PDF textbook into sequential, linked Obsidian notes:
one note per section, with a summary, a plain-language explanation, the
formulas, the figures cropped from the page, a bilingual glossary and the
pitfalls the source warns about. A *glosator* is the person who writes
glosses on a difficult text, which is exactly the job.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/glosator)

{{< hr >}}

**tachygraf** – the sibling of glosator, for recordings instead of books. It
turns a recorded lecture into a verbatim transcript and a set of linked study
notes, with a timestamp and a block ID on every paragraph, so every claim in a
note links back to the moment it was said. A *tachygraf* is the ancient
shorthand clerk who took speech down as it was spoken.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/tachygraf)

{{< hr >}}

## Shell and system

**GnuRAMage (gramage)** – a GNU RAM disk synchronization tool written in
bash: keeps a RAM disk in step with an HDD, with project exclusions.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/GnuRAMage)

[ <<< READ MORE >>> ](/projects/gnuramage/)

{{< hr >}}

**AutoGit-o-Matic** – periodically pulls or fetches git repositories, for
when the same work lives on several computers.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/AutoGit-o-Matic)

[ <<< READ MORE >>> ](/projects/autogitomatic/)

{{< hr >}}

**setup-DotFiles** – installs the packages, docker and dotfiles I want
immediately after a fresh Debian or Ubuntu install.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/setup-DotFiles)

[ <<< READ MORE >>> ](/projects/setupdotfiles/)

{{< hr >}}

**dockd-cmake3dot5-git** – my first AUR contribution: a packaging of the
Lenovo ThinkPad dock management daemon, built against the CMake version it
actually needs.

[ <<< AUR >>> ](https://aur.archlinux.org/packages/dockd-cmake3dot5-git)

[ <<< GitHub mirror >>> ](https://github.com/FPGArtktic/AUR_dockd-cmake3dot5-git-)

{{< hr >}}

## Notes and the web

**Copilot Export JSON to Markdown** – converts a GitHub Copilot JSON export
into Markdown, as a Python script and an Obsidian plugin.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/copilot-export-json-to-markdown)

[ <<< READ MORE >>> ](/projects/copilot-to-md/)

{{< hr >}}

**hugo-theme-c64-boot** – the theme this site is wearing. A Commodore 64 that
has just been switched on: the page is the screen, the navigation is the 1541
disk directory with real block counts, and the errors are the ones the machine
printed. No external requests, eight palettes, works without JavaScript.

[ <<< GitHub >>> ](https://github.com/FPGArtktic/hugo-theme-c64-boot)

[ <<< DEMO >>> ](https://fpgartktic.github.io/hugo-theme-c64-boot/)

{{< hr >}}
