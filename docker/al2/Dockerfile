FROM amazonlinux:2

# Packages & Users needed by Linuxbrew to run
RUN yum install -y curl wget file make ruby sudo which shadow-utils tar git gcc g++ \
    && yum clean all

RUN useradd -m -s /bin/bash ec2-user \
    && echo 'ec2-user ALL=(ALL) NOPASSWD:ALL' >>/etc/sudoers

USER ec2-user
WORKDIR /home/ec2-user

ENV USER=ec2-user

RUN wget -O ~/sam https://raw.githubusercontent.com/sanathkr/python-installer-experiments/master/sam
RUN chmod a+x ~/sam
RUN ~/sam upgrade

ENTRYPOINT ["/home/ec2-user/sam"]
CMD ["--help"]
