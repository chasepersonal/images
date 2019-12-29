FROM docker

RUN apk update \
    && apk add gcc libc-dev musl-dev jq python3 python3-dev py3-pip libffi-dev git vim openssl-dev \
    && pip3 install --upgrade pip \
    && pip3 install 'ansible==2.9.0.0'