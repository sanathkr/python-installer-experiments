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
