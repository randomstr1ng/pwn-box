FROM --platform=linux/amd64 ubuntu:22.04

# Install Packages
RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections && apt-get update && apt-get install -qy \
    git \
    wget \
    curl \
    nano \
    python3-pip \
    python3-dev \
    build-essential \
    gdb \
    binwalk \
    && rm -rf /var/lib/apt/lists/*

# Install Python Packages
RUN pip3 install pwntools

# Install gef
RUN bash -c "$(curl -fsSL https://gef.blah.cat/sh)"

# Finish setup
RUN echo "alias ll='ls -al --color=auto'" > /root/.bashrc
RUN echo "export PS1='\e[0;32m\u@pwn\e[m:\e[1;33m\w\e[m\n\$ '" >> /root/.bashrc
ENTRYPOINT ["/bin/bash"]