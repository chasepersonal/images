FROM debian:stretch-slim

RUN apt-get update \
    && apt-get install -y jq git software-properties-common \
    && apt-add-repository ppa:ansible/ansible \
    && apt-get install -y ansible