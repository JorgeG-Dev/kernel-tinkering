# Going with debian cause why not
FROM debian:trixie-slim

ENV DEBIAN_FRONTEND=noninteractive

# Dependencies specified as of Wrynose 6.0.1
RUN apt-get update && apt-get install -y \
    build-essential \
    chrpath \
    cpio \
    debianutils \
    diffstat \
    file \
    gawk \
    gcc \
    git \
    iputils-ping \
    libacl1 \
    libcrypt-dev \
    locales \
    python3 \
    python3-git \
    python3-jinja2 \
    python3-pexpect \
    python3-pip \
    python3-subunit \
    python3-websockets \
    socat \
    texinfo \
    unzip \
    wget \
    xz-utils \
    zstd

RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen && locale-gen

# Can't run bitbake as root, creating user for that
RUN useradd -m -s /bin/bash builder \
    && echo "builder ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
USER builder
WORKDIR /home/builder

RUN git clone https://git.openembedded.org/bitbake

VOLUME ["/home/builder/bitbake", "/home/builder/bitbake-builds"]
CMD ["/bin/bash"]
