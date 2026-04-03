FROM debian:sid-slim

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends --yes \
        sudo \
        wget \
        ca-certificates \
        iptables \
        qemu-utils \
        p7zip-full \
        openssh-server \
        htop \
        ethtool && \
    rm --recursive --force /var/lib/apt/lists/* && \
    update-alternatives --set iptables /usr/sbin/iptables-legacy && \
    update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy

# https://www.speedtest.net/apps/cli
# https://github.com/fastfetch-cli/fastfetch/actions/workflows/ci.yml?query=event%3Apush+is%3Asuccess+branch%3Adev
# https://pkgs.tailscale.com/unstable
# https://github.com/moby/moby/actions/workflows/buildkit.yml?query=event%3Apush+is%3Asuccess+branch%3Amaster
# https://github.com/docker/cli/actions/workflows/build.yml?query=event%3Apush+is%3Asuccess+branch%3Amaster
# https://github.com/containerd/containerd/actions/workflows/release.yml?query=event%3Apush+is%3Asuccess+branch%3Amain
# https://github.com/opencontainers/runc/actions/workflows/validate.yml?query=event%3Apush+is%3Asuccess+branch%3Amain
# https://github.com/docker/compose/actions/workflows/ci.yml?query=event%3Apush+is%3Asuccess+branch%3Amain
# https://github.com/docker/buildx/actions/workflows/build.yml?query=event%3Apush+is%3Asuccess+branch%3Amaster
# https://github.com/cli/cli/releases/latest
RUN mkdir --parents /usr/local/lib/docker/cli-plugins && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/speedtest --output-document /usr/local/bin/speedtest && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/fastfetch --output-document /usr/local/bin/fastfetch && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/tailscale --output-document /usr/local/bin/tailscale && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/tailscaled --output-document /usr/local/bin/tailscaled && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/docker-proxy --output-document /usr/local/bin/docker-proxy && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/dockerd --output-document /usr/local/bin/dockerd && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/docker-linux-amd64 --output-document /usr/local/bin/docker && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/containerd-shim-runc-v2 --output-document /usr/local/bin/containerd-shim-runc-v2 && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/containerd --output-document /usr/local/bin/containerd && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/runc.amd64 --output-document /usr/local/bin/runc && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/docker-compose-linux-x86_64 --output-document /usr/local/lib/docker/cli-plugins/docker-compose && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/buildx.linux-amd64 --output-document /usr/local/lib/docker/cli-plugins/docker-buildx && \
    wget https://github.com/ItzLevvie/artifacts/releases/latest/download/gh --output-document /usr/local/bin/gh && \
    chmod +x \
        /usr/local/bin/speedtest \
        /usr/local/bin/fastfetch \
        /usr/local/bin/tailscale \
        /usr/local/bin/tailscaled \
        /usr/local/bin/docker-proxy \
        /usr/local/bin/dockerd \
        /usr/local/bin/docker \
        /usr/local/bin/containerd-shim-runc-v2 \
        /usr/local/bin/containerd \
        /usr/local/bin/runc \
        /usr/local/lib/docker/cli-plugins/docker-compose \
        /usr/local/lib/docker/cli-plugins/docker-buildx \
        /usr/local/bin/gh
