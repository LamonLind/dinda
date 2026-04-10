FROM debian:bookworm-slim

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --yes --no-install-recommends \
        sudo \
        ca-certificates \
        wget \
        iptables \
        ethtool \
        qemu-utils \
        qemu-kvm \
        openssh-server \
        p7zip-full \
        htop && \
    rm -rf /var/lib/apt/lists/*

RUN update-alternatives --set iptables /usr/sbin/iptables-legacy && \
    update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
