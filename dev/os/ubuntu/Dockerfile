FROM debian:stretch-slim

ARG USERNAME=dev

RUN apt-get update && \
    apt-get install wget ssh dnsutils sudo vim git jq -y && \
    useradd -aG sudo $USERNAME 