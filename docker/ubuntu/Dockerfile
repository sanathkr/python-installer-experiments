FROM ubuntu:bionic

# Packages & Users needed by Linuxbrew to run
RUN apt-get update \
    && apt-get install -y --no-install-recommends ca-certificates wget git g++ curl locales make uuid-runtime \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -f UTF-8 en_US.UTF-8 \
    && useradd -m -s /bin/bash ubuntu \
    && echo 'ubuntu ALL=(ALL) NOPASSWD:ALL' >>/etc/sudoers

USER ubuntu
WORKDIR /home/ubuntu

RUN wget -O ~/sam https://raw.githubusercontent.com/sanathkr/python-installer-experiments/master/sam
RUN chmod a+x ~/sam
RUN ~/sam upgrade

ENTRYPOINT ["/home/ubuntu/sam"]
CMD ["--help"]
