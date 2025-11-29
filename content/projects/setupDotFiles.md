---
title: "setup-dotFiles - My personal dotfiles and configuration scripts for Ubuntu 24.04"
date: 2025-06-02 
---

setup-DotFiles is a collection of personal dotfiles and configuration scripts for quickly setting up an Ubuntu 24.04 and Arch Linux (I use arch, btw) development environment. The project automates the installation of essential packages, configures tools like git, tmux, and fzf, and applies custom settings for productivity and convenience.

## Key Features
- **Automated Package Installation:** Installs core packages such as git, build-essential, curl, and more.
- **Custom Configuration:** Sets up git global settings, tmux, bashrc, and fzf for a tailored workflow.
- **Docker Support:** Includes scripts and a Dockerfile for testing the setup in an isolated Ubuntu 24.04 container.
- **RAM Disk Setup:** Automates RAM disk configuration for high-speed temporary storage.
- **Easy Customization:** Uses simple text files and scripts for easy modification and extension.
- **Utility Scripts:** Includes VPN DNS tools and git hook templates for advanced users.

## Usage
- Clone the repository and run the setup script: `./setup-dotFiles.sh`
- Test in Docker
- Use flags like `--dry-run`, `-v/--verbose`, and `-y/--yes` for more control.

## Components
- `bashrc`: Custom bash configuration
- `tmux.conf`: TMUX configuration
- `apt-apps.txt`: List of packages to install 
- `yay-apps.txt`: List of packages to install
- `fzf.bash`: Fuzzy Finder configuration
- Utility scripts and templates

## License
setup-DotFiles is released under the GNU GPL v3.0 license.

For more details, visit the [setup-DotFiles GitHub repository](https://github.com/FPGArtktic/setup-DotFiles).
