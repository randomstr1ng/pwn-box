FROM --platform=linux/amd64 ubuntu:22.04

# Install Packages
RUN apt update && apt install -qy \
    git \
    wget \
    curl \
    python3-pip \
    python3-dev \
    build-essential \
    gdb \
    binwalk \
    && rm -rf /var/lib/apt/lists/*

# Install Python Packages \
RUN python3 -m pip install --upgrade \
    pip \
    pwntools \
    --break-system-packages

# Install gef
RUN bash -c "$(curl -fsSL https://gef.blah.cat/sh)"

# Finish setup
RUN echo "alias ll='ls -al --color=auto'" > /root/.bashrc
RUN echo "export PS1='\e[0;32m\u@sap-attack-surface\e[m:\e[1;33m\w\e[m\n\$ '" >> /root/.bashrc
ENTRYPOINT ["/bin/bash"]