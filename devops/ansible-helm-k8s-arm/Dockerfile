FROM armhf/alpine

COPY qemu-arm-static /usr/bin

ARG USERNAME=devel

RUN apk update \
    && apk add sudo curl openssl bash gcc libc-dev musl-dev jq python3 python3-dev py3-pip libffi-dev git vim openssl-dev tar \
    && pip3 install --upgrade pip \
    && pip3 install 'ansible==2.9.0.0' \
    && curl -LO https://get.helm.sh/helm-v3.0.3-linux-arm64.tar.gz \
    && tar -zxvf helm-v3.0.3-linux-arm64.tar.gz \
    && mv linux-arm64/helm /usr/local/bin/helm \
    && curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.17.0/bin/linux/arm/kubectl \
    && chmod +x kubectl \
    && mv kubectl /usr/bin/kubectl \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

WORKDIR /home/$USERNAME

USER $USERNAME