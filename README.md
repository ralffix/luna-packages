# 🌙 Luna OS Package Repository

Official package repository for Luna OS - the minimal, beautiful Linux distribution.

## What is this?

This repository contains the **package database** for Luna OS. The `packages.json` file lists all available packages that can be installed with the `luna` package manager.

## Using packages

On Luna OS:

```bash
# Update package list
luna update

# Search for packages
luna search python

# Install packages
luna install python3
luna install wget curl vim

# List installed packages
luna list

# Remove packages
luna remove python3
```

## Package Format

Each package in `packages.json` follows this structure:

```json
{
  "name": "package-name",
  "version": "1.0.0",
  "url": "https://download-url.com/package.tar.gz",
  "type": "binary|tarball|source",
  "description": "Package description",
  "dependencies": []
}
```

### Package Types

- **binary**: Pre-compiled executable (fastest, recommended)
- **tarball**: Archive with binaries to extract
- **source**: Source code (requires compilation with gcc/make)

## Contributing Packages

Want to add a package to Luna OS? Here's how:

### 1. Fork this repository

### 2. Add your package to `packages.json`

Example for a binary package:
```json
{
  "name": "mytool",
  "version": "1.0.0",
  "url": "https://github.com/user/mytool/releases/download/v1.0/mytool-linux-amd64",
  "type": "binary",
  "description": "My awesome tool",
  "dependencies": []
}
```

Example for a tarball:
```json
{
  "name": "anothertool",
  "version": "2.1.0",
  "url": "https://github.com/user/anothertool/releases/download/v2.1.0/anothertool-linux.tar.gz",
  "type": "tarball",
  "description": "Another great tool",
  "dependencies": []
}
```

### 3. Test your package

```bash
# On Luna OS
luna update
luna install mytool
mytool --version  # verify it works
```

### 4. Submit a Pull Request

- Keep package names lowercase
- Use official download URLs
- Prefer `binary` type for faster installs
- Add a clear description
- List dependencies if any

## Package Guidelines

### ✅ Good packages:
- Static binaries (no external dependencies)
- Small footprint (<50MB)
- Work on x86_64 Linux
- Stable release versions
- Direct download URLs (no login required)

### ❌ Avoid:
- Packages requiring GUI (Luna OS is minimal)
- Packages >200MB
- Beta/unstable versions
- URLs requiring authentication
- Malware or untrusted sources

## Available Packages

Currently in the repository:

**Development Tools:**
- python3, git, vim, nano, micro

**System Utilities:**
- wget, curl, htop, neofetch

**Modern CLI Tools:**
- jq (JSON processor)
- fzf (fuzzy finder)
- bat (cat with colors)
- ripgrep (fast grep)
- fd (fast find)
- exa (modern ls)

## Repository URL

The Luna package manager fetches from:
```
https://raw.githubusercontent.com/ralffix/luna-packages/main/packages.json
```

## Questions?

- **Issues**: Report problems with packages here
- **Discord**: Join the Luna OS community (coming soon!)
- **Docs**: See the main Luna OS repo for documentation

---

**Built with 💙 by the Luna OS community**

🌙 *Making Linux beautiful, one package at a time*
