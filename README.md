# python-installer-experiments
How can I create a self-contained Python application installer for Linux?

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

### Installing in Docker
To run inside Linux Docker (say Ubuntu), you need to create a new user that is not "root" because Homebrew will fail if you run as root. Explore the following Dockerfiles to get instructions to add a new non-root user before running the installation instructions: https://github.com/Linuxbrew/docker
