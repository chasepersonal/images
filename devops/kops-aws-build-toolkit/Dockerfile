FROM alpine:3.11.3

ARG USERNAME=dev

RUN apk update \
    && apk add --no-cache unzip \
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
    tar \
    util-linux \
    jq \
    openssh-client \
    openssl-dev \
    && wget https://releases.hashicorp.com/terraform/0.12.12/terraform_0.12.12_linux_amd64.zip \
    && unzip terraform_0.12.12_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/ \
    && rm -rf terraform_0.12.12_linux_amd64.zip \
    && pip3 install --upgrade pip \
    && pip3 install awscli boto boto3 openshift 'PyYAML==3.12' 'ansible==2.9.0.0' \
    && curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.17.0/bin/linux/amd64/kubectl \
    && chmod +x kubectl \
    && mv kubectl /bin/kubectl \
    && curl -LO https://get.helm.sh/helm-v3.0.3-linux-amd64.tar.gz \
    && tar -zxvf helm-v3.0.3-linux-amd64.tar.gz \
    && mv linux-amd64/helm /usr/local/bin/helm \
    && rm -rf helm-v3.0.3-linux-amd64.tar.gz \
    && curl -Lo kops https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64 \
    && chmod +x ./kops \
    && mv ./kops /usr/local/bin/ \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && mkdir /home/$USERNAME/workspace \
    && chown -R $USERNAME:$USERNAME /home/$USERNAME/workspace

USER $USERNAME

WORKDIR /home/$USERNAME/workspace

RUN mkdir ~/.aws \
    && chown -R $USERNAME:$USERNAME ~/.aws