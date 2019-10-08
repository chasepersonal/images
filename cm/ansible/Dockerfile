FROM debian:stretch-slim

RUN apt-get update \
    && apt-get install -y python3-pip jq git software-properties-common \
    && pip3 install 'ansible==2.8.5.0'