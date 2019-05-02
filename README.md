# python-installer-experiments
How can I create a self-contained Python application installer for Linux?

This repository contains examples of doing this for AWS SAM CLI tool using [Linuxbrew](https://docs.brew.sh/Homebrew-on-Linux) package manager. Linuxbrew is an official port of Homebrew MacOS package manager for Linux. It can be installed inside a home directory (no sudo needed), does not use any system libraries (except glibc and gcc). Installations within the Linuxbrew environment are self-contained, not exposed to the $PATH (unless you choose to), and easily removable.

## AWS SAM CLI

**Pre-reqs**: wget git gcc

```bash
# Installation
wget -O ~/sam https://raw.githubusercontent.com/sanathkr/python-installer-experiments/master/sam
chmod a+x ~/sam
alias sam=~/sam

# Usage
sam --version

# Upgrade
sam upgrade
```

### Docker

#### Ubuntu

```
docker build -t sam:ubuntu ./docker/ubuntu/Dockerfile
docker run sam:ubuntu --help
```

#### AmazonLinux 2

```
docker build -t sam:al2 ./docker/al2/Dockerfile
docker run sam:al2 --help
```

#### Lambci

```
docker build -t sam:lambci-ruby2.5 ./docker/al2/Dockerfile
docker run sam:lambci-ruby2.7 --help
```

### Native Installers

Native installers like **deb** &  **rpm** packages can be easily built by wrapping the Install Script within the package managers. The installer will simply copy the shell script to appropriate location and do a fresh Linuxbrew+SAMCLI install. The shell script is self-sufficient to run SAM CLI and upgrade it in future.
