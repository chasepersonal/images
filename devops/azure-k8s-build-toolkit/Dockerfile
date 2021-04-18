FROM debian:buster-slim

ARG USERNAME=dev

SHELL ["/bin/bash", "-c"]

RUN apt-get update \
    && apt-get install -y curl \
    wget \
    git \
    vim \
    tar \
    unzip \
    jq \
    python3 \
    python3-pip \
    build-essential \
    libssl-dev\
    libffi-dev \
    python3-dev \
    ca-certificates \
    apt-transport-https \
    lsb-release \
    gnupg \
    openssh-server \
    && curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null \
    && AZ_REPO=$(lsb_release -cs) \
    && echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | tee /etc/apt/sources.list.d/azure-cli.list \
    && apt-get update \
    && apt-get install -y azure-cli \
    && wget https://releases.hashicorp.com/terraform/0.14.7/terraform_0.14.7_linux_amd64.zip \
    && unzip terraform_0.14.7_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/ \
    && rm -rf terraform_0.14.7_linux_amd64.zip \
    && pip3 install --upgrade pip \
    && pip3 install boto boto3 openshift 'PyYAML==3.12' 'ansible==2.9.0.0' \
    && curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.19.0/bin/linux/amd64/kubectl \
    && chmod +x kubectl \
    && mv kubectl /bin/kubectl \
    && curl -LO https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz \
    && tar -zxvf helm-v3.5.2-linux-amd64.tar.gz \
    && mv linux-amd64/helm /usr/local/bin/helm \
    && rm -rf helm-v3.5.2-linux-amd64.tar.gz \
    && adduser --disabled-password --gecos "" $USERNAME \
    && mkdir /home/$USERNAME/workspace \
    && chown -R $USERNAME:$USERNAME /home/$USERNAME/workspace \
    && VERSION=$(curl --silent "https://api.github.com/repos/argoproj/argo-cd/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/') \
    && curl -sSL -o /usr/local/bin/argocd https://github.com/argoproj/argo-cd/releases/download/$VERSION/argocd-linux-amd64 \
    && chmod +x /usr/local/bin/argocd \
    && echo "export ANSIBLE_CONFIG=$HOME/ansible-config/ansible.cfg" >> /home/$USERNAME/.bashrc \
    && source /home/$USERNAME/.bashrc

USER $USERNAME

WORKDIR /home/$USERNAME/workspace