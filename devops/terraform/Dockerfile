FROM alpine:3.10.2

RUN apk update \
    && apk add unzip wget \
    && wget https://releases.hashicorp.com/terraform/0.12.12/terraform_0.12.12_linux_amd64.zip \
    && unzip terraform_0.12.12_linux_amd64.zip \
    && chmod +x terraform \
    && mv terraform /usr/local/bin/