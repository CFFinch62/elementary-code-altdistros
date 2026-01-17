# Contributing to Elementary Code for Linux

Thank you for your interest in making Elementary Code more accessible on Linux distributions!

## How to Contribute

There are many ways to contribute to this project:

### 🐛 Report Bugs

Found a build or installation issue? Please report it!

**Before reporting:**
1. Check [FAQ.md](FAQ.md) for common issues
2. Search existing issues to avoid duplicates
3. Make sure you're using the latest version

**When reporting:**
- Use the bug report template in `.github/ISSUE_TEMPLATE/`
- Include your distribution and version: `cat /etc/os-release`
- Provide complete error messages
- List steps to reproduce
- Mention what you expected vs what happened

### 📝 Improve Documentation

Documentation improvements are always welcome:

- Fix typos or unclear instructions
- Add troubleshooting tips
- Improve installation guides
- Translate documentation
- Add screenshots or examples

**How to submit:**
1. Fork the repository
2. Edit the markdown files
3. Test your changes (make sure links work)
4. Submit a pull request

### 🧪 Test on Different Distributions

Help us support more distributions:

1. Try building on your distribution
2. Document any issues or required changes
3. Share package names for dependencies
4. Report success or failure

**Distributions we'd love to support:**
- Fedora / RHEL / CentOS
- Arch Linux / Manjaro
- openSUSE
- Pop!_OS
- Zorin OS
- Other Debian/Ubuntu derivatives

### 📦 Create Packages

Package maintainers wanted!

- **DEB packages** for Debian/Ubuntu/Mint
- **RPM packages** for Fedora/RHEL
- **AUR packages** for Arch
- **AppImage** for universal distribution
- **Flatpak** for sandboxed installation

See the `packaging/` directory for starting points.

### 🔧 Fix Build Issues

Help improve the build process:

- Fix compatibility issues
- Improve error messages
- Add support for more distributions
- Optimize build scripts
- Add automated tests

### 💻 Improve Scripts

The installation scripts can always be better:

- Better error handling
- More informative output
- Support for more edge cases
- Dependency version detection
- Automated testing

## Development Setup

### Prerequisites

- Git
- Basic shell scripting knowledge (for scripts)
- Familiarity with meson/ninja (for build system)

### Getting Started

1. **Fork the repository** on GitHub

2. **Clone your fork:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/code-8.1.2-lm.git
   cd code-8.1.2-lm
   ```

3. **Create a branch:**
   ```bash
   git checkout -b my-improvement
   ```

4. **Make your changes**

5. **Test your changes:**
   ```bash
   # Test build scripts
   ./scripts/build.sh --clean
   
   # Test installation
   ./scripts/install.sh
   
   # Test on a clean system if possible
   ```

6. **Commit your changes:**
   ```bash
   git add .
   git commit -m "Description of your changes"
   ```

7. **Push to your fork:**
   ```bash
   git push origin my-improvement
   ```

8. **Create a pull request** on GitHub

## Code Style

### Shell Scripts

- Use `#!/bin/bash` shebang
- Use `set -e` for error handling
- Add comments for complex logic
- Use meaningful variable names
- Include error messages with colors
- Test on both bash and sh if possible

Example:
```bash
#!/bin/bash
set -e

# Colors
GREEN='\033[0;32m'
NC='\033[0m'

# Check for required tool
if ! command -v meson &> /dev/null; then
    echo -e "${RED}Error: meson not found${NC}"
    exit 1
fi
```

### Documentation

- Use GitHub Flavored Markdown
- Keep lines under 120 characters
- Use code blocks with language specification
- Include examples where helpful
- Use alerts (NOTE, WARNING, etc.) for important info

Example:
```markdown
> [!WARNING]
> This command will delete all build files.
```

## Testing

### Manual Testing

Before submitting, test on:

1. **Fresh system** (VM recommended)
2. **Your target distribution**
3. **Both clean install and upgrade scenarios**

### Test Checklist

- [ ] Scripts are executable (`chmod +x`)
- [ ] Scripts run without errors
- [ ] Documentation is accurate
- [ ] Links work correctly
- [ ] Code blocks are properly formatted
- [ ] Changes work on target distribution

## Pull Request Guidelines

### Good Pull Requests

- **Focused**: One feature/fix per PR
- **Tested**: Verified to work
- **Documented**: Update relevant docs
- **Described**: Clear description of changes

### PR Description Template

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Build script improvement

## Testing
- Distribution tested on: Linux Mint 22.3
- Test results: All scripts work correctly

## Checklist
- [ ] Scripts are executable
- [ ] Documentation updated
- [ ] Tested on target distribution
- [ ] No breaking changes
```

## Reporting Issues

### Build/Installation Issues

Use `.github/ISSUE_TEMPLATE/build_issue.md`

Include:
- Distribution and version
- Complete error output
- Steps you followed
- What you expected

### Bug Reports

Use `.github/ISSUE_TEMPLATE/bug_report.md`

Include:
- Description of the bug
- Steps to reproduce
- Expected vs actual behavior
- System information

### Feature Requests

Open a regular issue with:
- Clear description of the feature
- Use case / why it's needed
- Proposed implementation (if any)

## Code of Conduct

### Be Respectful

- Be kind and courteous
- Respect different opinions
- Provide constructive feedback
- Help newcomers

### Be Professional

- Stay on topic
- Avoid spam or self-promotion
- Don't post offensive content
- Respect maintainer decisions

## Questions?

- **General questions**: Open a discussion on GitHub
- **Build issues**: Check [FAQ.md](FAQ.md) first
- **Documentation**: Read [INSTALL_LINUX_MINT.md](INSTALL_LINUX_MINT.md) and [DEPENDENCIES.md](DEPENDENCIES.md)

## Recognition

Contributors will be recognized in:
- GitHub contributors page
- Release notes (for significant contributions)
- This README (for major features/fixes)

## License

By contributing, you agree that your contributions will be licensed under the GPL-3.0 license, the same as Elementary Code.

---

Thank you for contributing to make Elementary Code available to more Linux users! 🎉
