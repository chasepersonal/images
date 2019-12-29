FROM armhf/alpine

COPY qemu-arm-static /usr/bin

ARG USERNAME=devel

RUN apk update \
    && apk add curl openssl bash gcc libc-dev musl-dev jq python3 python3-dev py3-pip libffi-dev git vim openssl-dev \
    && pip3 install --upgrade pip \
    && pip3 install 'ansible==2.9.0.0' \
    && curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME

WORKDIR /home/$USERNAME

USER $USERNAME