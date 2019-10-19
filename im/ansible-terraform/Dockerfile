FROM alpine:3.10.2

RUN apk update \
    && apk add unzip \
    wget \
    gcc \
    libc-dev \
    musl-dev \
    python3 \
    python3-dev \
    py3-pip \
    libffi-dev \
    git \
    vim \
    openssl-dev \
    && wget https://releases.hashicorp.com/terraform/0.12.12/terraform_0.12.12_linux_amd64.zip \
    && unzip terraform_0.12.12_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/ \
    && pip3 install --upgrade pip \
    && pip3 install 'ansible==2.8.5.0'