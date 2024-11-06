ARG ALPINE_TAG=latest
FROM alpine:${ALPINE_TAG}

LABEL maintainer="bittus <https://hub.docker.com/repository/docker/bittus>" \
    description="A Docker image with most of devops tools pre-installed."

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
    postgresql-client \
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
    py3-pip \
    docker 
    # gcc python3-dev musl-dev linux-headers
# RUN python3 -m venv /venv \
#     && . /venv/bin/activate \
#     && pip install --no-cache-dir azure-cli    
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
RUN install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
CMD ["/bin/bash", "-ec", "while :; do echo '.'; sleep 5 ; done"]
#CMD ["/bin/bash", "--login"]