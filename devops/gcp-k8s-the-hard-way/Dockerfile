FROM google/cloud-sdk:latest

RUN apt-get update -y \
    && apt-get upgrade -y \
    && apt-get install jq git wget vim tmux -y \
    && wget -q --show-progress --https-only --timestamping \
    https://storage.googleapis.com/kubernetes-the-hard-way/cfssl/linux/cfssl \
    https://storage.googleapis.com/kubernetes-the-hard-way/cfssl/linux/cfssljson \
    && chmod +x cfssl cfssljson \
    && mv cfssl cfssljson /usr/local/bin/