FROM docker

ARG USERNAME=dev

RUN apk update \
    && apk add gcc \
    libc-dev \
    musl-dev \
    jq \
    python3 \
    python3-dev \
    py3-pip \
    libffi-dev \
    git \
    vim \
    openssl-dev \
    && pip3 install --upgrade pip \
    && pip3 install 'ansible==2.9.0.0' \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME \
    && mkdir /home/$USERNAME/workspace \
    && chown -R $USERNAME:$USERNAME /home/$USERNAME/workspace \
    && mkdir /etc/ansible

COPY ansible.cfg /etc/ansible/ansible.cfg

USER $USERNAME

WORKDIR /home/$USERNAME/workspace