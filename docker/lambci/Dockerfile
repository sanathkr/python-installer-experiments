FROM lambci/lambda:build-ruby2.5

# Packages & Users needed by Linuxbrew to run
RUN yum install -y curl wget file make ruby sudo which shadow-utils tar git gcc g++ \
    && yum clean all

RUN useradd -m -s /bin/bash samuser \
    && echo 'samuser ALL=(ALL) NOPASSWD:ALL' >>/etc/sudoers

USER samuser
WORKDIR /home/samuser

RUN wget -O ~/sam https://raw.githubusercontent.com/sanathkr/python-installer-experiments/master/sam
RUN chmod a+x ~/sam
RUN ~/sam upgrade

ENTRYPOINT ["/home/samuser/sam"]
CMD ["--help"]
