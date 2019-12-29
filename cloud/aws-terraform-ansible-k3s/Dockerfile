FROM alpine:3.10.2

ARG USERNAME=dev

RUN apk update \
    && apk add unzip \
    sudo \
    wget \
    curl \
    gcc \
    libc-dev \
    musl-dev \
    python3 \
    python3-dev \
    py3-pip \
    libffi-dev \
    git \
    vim \
    openssh-client \
    openssl-dev \
    && wget https://releases.hashicorp.com/terraform/0.12.12/terraform_0.12.12_linux_amd64.zip \
    && unzip terraform_0.12.12_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/ \
    && pip3 install --upgrade pip \
    && pip3 install awscli boto boto3 'ansible==2.9.0.0' \
    && curl -sLS https://raw.githubusercontent.com/alexellis/k3sup/master/get.sh  | sh \
    && rm -rf terraform_0.12.12_linux_amd64.zip \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER dev