# Elementary Code for Linux Mint
[![Translation status](https://l10n.elementary.io/widgets/code/-/svg-badge.svg)](https://l10n.elementary.io/projects/code/?utm_source=widget)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](COPYING)

![Screenshot](data/screenshot.png?raw=true)

A fast, lightweight code editor designed for Elementary OS, now easily installable on **Linux Mint** and other Linux distributions.

## Quick Installation (Linux Mint)

For Linux Mint users, installation is simple:

```bash
./scripts/quick-install-mint.sh
```

This will automatically install dependencies, build, and install Elementary Code on your system.

## Installation Guides

- **[Linux Mint Installation Guide](INSTALL_LINUX_MINT.md)** - Detailed guide for Linux Mint 21.x and 22.x
- **[General Linux Installation Guide](INSTALL_LINUX.md)** - For Ubuntu, Debian, Fedora, Arch, and other distributions
- **[Dependencies Reference](DEPENDENCIES.md)** - Complete dependency list and cross-distribution package names

## Manual Installation

### Install Dependencies

**Linux Mint / Ubuntu / Debian:**
```bash
./scripts/install-dependencies-mint.sh
```

Or install manually (see [DEPENDENCIES.md](DEPENDENCIES.md) for your distribution).

### Build

```bash
./scripts/build.sh
```

Or manually:
```bash
meson setup build --prefix=/usr
cd build
ninja
```

### Install

```bash
./scripts/install.sh
```

Or manually:
```bash
cd build
sudo ninja install
```

### Run

```bash
io.elementary.code
```

Or find "Code" in your application menu.

## Features

- **Syntax Highlighting** - Support for 300+ programming languages
- **Git Integration** - Built-in Git support
- **Plugin System** - Extensible with plugins
- **Terminal** - Integrated terminal emulator
- **Multiple Panes** - Split view editing
- **Auto-save** - Never lose your work
- **EditorConfig** - Respect project coding styles
- **Spell Checking** - Built-in spell checker

## Documentation

- **[FAQ](FAQ.md)** - Frequently asked questions and troubleshooting
- **[Contributing](CONTRIBUTING.md)** - How to contribute to this project
- **[License](COPYING)** - GPL-3.0 License

## System Requirements

- Linux Mint 21.x or 22.x (or equivalent Ubuntu/Debian)
- 2GB free disk space for building
- GTK 3.6+
- See [DEPENDENCIES.md](DEPENDENCIES.md) for complete requirements

## Uninstalling

```bash
./scripts/uninstall.sh
```

## Getting Help

- Check [FAQ.md](FAQ.md) for common issues
- Read the installation guides
- Open an issue on GitHub with your distribution and error details

## About This Project

This project provides build scripts, documentation, and packaging to make Elementary Code easily accessible on Linux Mint and other Linux distributions. The core Elementary Code is developed by [Elementary](https://github.com/elementary/code).

## License

Elementary Code is licensed under the [GNU General Public License v3.0](COPYING).

---

**Enjoy coding!** 💻
