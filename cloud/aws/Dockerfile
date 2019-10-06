FROM debian:stretch-slim

# Install python with pip, jq, git, awscli
RUN apt-get update \ 
    && apt-get install -y python3-pip jq git \
    && pip3 install awscli 