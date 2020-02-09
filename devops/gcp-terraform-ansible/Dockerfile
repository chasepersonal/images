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
    which \
    bash \
    openssh-client \
    openssl-dev \
    curl \
    && wget https://releases.hashicorp.com/terraform/0.12.12/terraform_0.12.12_linux_amd64.zip \
    && unzip terraform_0.12.12_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/ \
    && rm -rf terraform_0.12.12_linux_amd64.zip \
    && curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.17.0/bin/linux/amd64/kubectl \
    && chmod +x kubectl \
    && mv kubectl /bin/kubectl \
    && pip3 install --upgrade pip \
    && pip3 install boto boto3 'ansible==2.8.5.0' \
    && curl -sSL https://sdk.cloud.google.com | bash -s -- --disable-prompts --install-dir=/usr/local/gcloud

ENV PATH $PATH:/usr/local/gcloud/google-cloud-sdk/bin