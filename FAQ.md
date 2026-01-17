# Frequently Asked Questions (FAQ)

## General Questions

### What is Elementary Code?

Elementary Code is a fast, lightweight code editor designed for Elementary OS. This project makes it available for other Linux distributions, particularly Linux Mint.

### Is this the official Elementary Code?

This is the official Elementary Code source code (version 8.1.2), adapted with build scripts and documentation to make it easy to compile and install on Linux Mint and other Linux distributions.

### What's the difference between this and the Elementary OS version?

The core editing functionality is identical. However, some Elementary OS-specific integrations may not work on other distributions:

- **Contractor integration** - Elementary's system-wide sharing/actions framework
- **Elementary styling** - Some visual elements may look different
- **System settings integration** - Elementary OS settings panel integration

All core features work perfectly: syntax highlighting, plugins, Git integration, terminal, etc.

### Why isn't this in the official repositories?

Elementary Code is designed primarily for Elementary OS. While it can be compiled for other distributions, it's not officially packaged for them. This project provides the tools to build it yourself.

## Installation Questions

### Which installation method should I use?

**For Linux Mint users**: Use the quick installer:
```bash
./scripts/quick-install-mint.sh
```

**For other distributions**: Follow the manual steps in [INSTALL_LINUX.md](INSTALL_LINUX.md)

**For maximum compatibility**: Use Flatpak (if available)

### Do I need to compile from source?

Currently, yes. We provide scripts to make this easy. In the future, we may provide pre-built packages (DEB, AppImage) in the releases section.

### How much disk space do I need?

- **Dependencies**: ~200-300 MB
- **Build files**: ~100-150 MB
- **Installed application**: ~50 MB

Total: ~400-500 MB during installation, ~50 MB after cleanup.

### How long does compilation take?

On a modern system:
- **Dependency installation**: 2-5 minutes
- **Compilation**: 2-3 minutes
- **Total**: 5-10 minutes

Older systems may take longer.

## Build Issues

### "Package libgranite-dev not found"

Granite is an Elementary OS library. On Linux Mint/Ubuntu, add the Elementary PPA:

```bash
sudo add-apt-repository ppa:elementary-os/stable
sudo apt update
sudo apt install libgranite-dev
```

The dependency installer script does this automatically.

### "Package libpeas-2-dev not found"

Older distributions (Ubuntu 22.04, Linux Mint 21) use libpeas-1:

```bash
sudo apt install libpeas-dev
```

The dependency installer script handles this automatically.

### "Vala version too old"

Check your Vala version:
```bash
valac --version
```

You need Vala 0.48 or higher. On older systems:

```bash
sudo add-apt-repository ppa:vala-team/next
sudo apt update
sudo apt install valac
```

### Build fails with "ninja: command not found"

Install ninja:
```bash
sudo apt install ninja-build
```

### "Permission denied" during installation

Use sudo for installation:
```bash
sudo ./scripts/install.sh
```

Or if running manually:
```bash
cd build
sudo ninja install
```

### Build succeeds but application doesn't appear in menu

Update the desktop database:
```bash
sudo update-desktop-database
sudo gtk-update-icon-cache /usr/share/icons/hicolor
```

The install script does this automatically.

## Usage Questions

### How do I run Elementary Code?

After installation:
- **From menu**: Search for "Code" in your application launcher
- **From terminal**: `io.elementary.code`
- **Open a file**: `io.elementary.code /path/to/file`

### Can I set it as my default text editor?

Yes! Right-click a text file → Properties → Open With → Select "Code" and set as default.

Or from terminal:
```bash
xdg-mime default io.elementary.code.desktop text/plain
```

### Does it support plugins?

Yes! Elementary Code has a plugin system. Plugins are located in:
- System: `/usr/share/io.elementary.code/plugins/`
- User: `~/.local/share/io.elementary.code/plugins/`

### How do I update to a newer version?

```bash
cd /path/to/code-8.1.2-lm
git pull
./scripts/build.sh --clean
./scripts/install.sh
```

### How do I uninstall?

```bash
./scripts/uninstall.sh
```

Or manually:
```bash
cd build
sudo ninja uninstall
```

## Compatibility Questions

### Which Linux distributions are supported?

**Tested and supported:**
- Linux Mint 21.x, 22.x
- Ubuntu 22.04, 24.04
- Debian 12+

**Should work (untested):**
- Fedora 38+
- Arch Linux
- openSUSE Tumbleweed
- Other modern Linux distributions

### Does it work on Wayland?

Yes! Elementary Code works on both X11 and Wayland.

### Does it work on ARM (Raspberry Pi)?

It should compile on ARM, but this is untested. Dependencies must be available for your architecture.

### Can I run it on Windows or macOS?

No, Elementary Code is Linux-only. For Windows/macOS, consider:
- Visual Studio Code
- Sublime Text
- Atom (discontinued)

## Troubleshooting

### Application crashes on startup

Check for missing dependencies:
```bash
ldd /usr/local/bin/io.elementary.code
```

Look for "not found" entries.

### Syntax highlighting doesn't work

GtkSourceView language specs should be installed automatically. If not:
```bash
sudo apt install gtksourceview-4-common
```

### Git integration doesn't work

Ensure libgit2-glib is installed:
```bash
sudo apt install libgit2-glib-1.0-0
```

### Terminal plugin doesn't work

Ensure VTE is installed:
```bash
sudo apt install libvte-2.91-0
```

### Spell checking doesn't work

Install gtkspell:
```bash
sudo apt install libgtkspell3-3-0
```

And install dictionaries:
```bash
sudo apt install hunspell hunspell-en-us
```

## Contributing

### How can I help?

- **Test on different distributions** and report results
- **Report bugs** with detailed information
- **Improve documentation** with corrections or additions
- **Create packages** (DEB, RPM, etc.)
- **Submit patches** for build issues

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### I found a bug in the editor itself

If it's a bug in Elementary Code (not the build process), report it to the upstream project:
https://github.com/elementary/code

If it's a build/installation issue for Linux Mint, report it here.

### Can I donate?

This is a community project to make Elementary Code accessible on more distributions. If you want to support Elementary Code development, consider supporting Elementary OS:
https://elementary.io/

## License

### What license is this under?

Elementary Code is licensed under GPL-3.0. See [COPYING](COPYING) for full details.

### Can I use this commercially?

Yes! The GPL-3.0 license allows commercial use. You can:
- Use it for commercial development
- Distribute it commercially
- Modify it for commercial purposes

You must:
- Keep the GPL-3.0 license
- Provide source code if you distribute it
- Document your changes

### Can I redistribute this?

Yes! You can redistribute Elementary Code under the GPL-3.0 license. If you modify it, you must:
- Keep the GPL-3.0 license
- Provide source code
- Document your changes

## Getting More Help

### Where can I get support?

1. **Check this FAQ** first
2. **Read the documentation**: [INSTALL_LINUX_MINT.md](INSTALL_LINUX_MINT.md), [DEPENDENCIES.md](DEPENDENCIES.md)
3. **Search existing issues** on GitHub
4. **Open a new issue** with:
   - Your Linux distribution and version
   - Complete error messages
   - Steps to reproduce

### How do I report a bug?

Open an issue on GitHub with:
- **System info**: `cat /etc/os-release`
- **Error messages**: Complete output
- **Steps to reproduce**: What you did before the error
- **Expected vs actual**: What should happen vs what happened

Use the issue templates provided in `.github/ISSUE_TEMPLATE/`.
