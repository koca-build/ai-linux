# AI Linux Packages

This repository contains `.deb` and `.rpm` repositories for various AI-related tools and applications on Linux. Packages are automatically built and published to Debian and RPM repositories hosted via GitHub Pages.

[![claude-code](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fai-linux.koca.dev%2Fversions.json&query=%24.%22claude-code%22&label=claude-code&color=orange)](https://ai-linux.koca.dev)
[![gemini-cli](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fai-linux.koca.dev%2Fversions.json&query=%24.%22gemini-cli%22&label=gemini-cli&color=purple)](https://ai-linux.koca.dev)

## Installation

### Debian/Ubuntu

To use this repository on your Debian-based system (Ubuntu, Linux Mint, Debian, etc.), follow the steps below.

#### 1. Add the Repository

```bash
wget -qO - https://ai-linux.koca.dev/repo.key | gpg --dearmor | sudo tee /usr/share/keyrings/ai-linux.gpg > /dev/null
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/ai-linux.gpg] https://ai-linux.koca.dev/deb stable main" > /etc/apt/sources.list.d/ai-linux.list'
```

#### 2. Update and Install

After adding the repository, update your package index and install the desired packages:

```bash
sudo apt update
sudo apt install <package-name>
```

### Fedora/CentOS/RHEL

To use this repository on your RPM-based system (Fedora, CentOS, RHEL, etc.), follow the steps below.

#### 1. Add the Repository

```bash
sudo rpm --import https://ai-linux.koca.dev/repo.key
sudo sh -c 'echo -e "[ai-linux]\nname=ai-linux repository\nbaseurl=https://ai-linux.koca.dev/rpm\nenabled=1\ngpgcheck=0\nrepo_gpgcheck=0" > /etc/yum.repos.d/ai-linux.repo'
```

#### 2. Install

After adding the repository, you can install the desired packages:

```bash
sudo dnf install <package-name>
```

## Contributing

To add a new package or update an existing one:

1.  Create or modify [a `.koca` file](https://github.com/koca-build/koca) in the `koca/` directory.
2.  Push your changes to the `main` branch.
3.  The GitHub Actions workflow will automatically build the package, create a GitHub Release, and update the Debian and RPM repositories.

## License

The build scripts in this repository are released under the [MIT License](LICENSE).
