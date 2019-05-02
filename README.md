# python-installer-experiments
How can I create a self-contained Python application installer for Linux?

## AWS SAM CLI
```bash
# Installation
wget -O ~/sam https://raw.githubusercontent.com/sanathkr/python-installer-experiments/master/sam
chmod a+x ~/sam
alias sam=~/sam

# Usage
sam —version

# Upgrade
sam upgrade
```
