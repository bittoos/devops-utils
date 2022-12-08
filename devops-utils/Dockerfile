ARG ALPINE_TAG=latest
FROM alpine:${ALPINE_TAG}

LABEL maintainer="bittus <https://hub.docker.com/repository/docker/bittus>" \
    description="A Docker image with various devops tools pre-installed."

RUN apk -U upgrade && apk add --no-cache \
    apache2-utils \
    bash \
    bash-completion \
    bind-tools \
    busybox-extras \
    ca-certificates \
    coreutils \
    curl \
    drill \
    findutils \
    fping \
    elinks \
    git \
    ipcalc \
    iperf \
    iproute2 \
    iputils \
    jq \
    libidn \
    macchanger \
    mtr \
    mysql-client \
    net-tools \
    netcat-openbsd \
    ngrep \
    nload \
    nmap \
    nmap-scripts \
    oath-toolkit-oathtool \
    openssh-client \
    openssl \
    procps \
    socat \
    tcpdump \
    tshark \
    wget \
    python3 \
    && apk add arp-scan --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing/ --no-cache \
    && apk add --update docker openrc && rc-update add docker boot \
    && python3 -m ensurepip \
    && pip3 install --upgrade pip \
    && python3 -m pip install requests \
    && rm -rf /var/cache/apk/* \
    && echo 'export PS1="[docker@devops-tools]\$ "' >> /root/.bash_profile
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
RUN install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
CMD ["/bin/bash", "-ec", "while :; do echo '.'; sleep 5 ; done"]
#CMD ["/bin/bash", "--login"]
