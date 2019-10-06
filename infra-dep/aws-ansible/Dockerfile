FROM debian:stretch-slim

# Install python with pip, jq, git, awscli, ansible
RUN apt-get update \ 
    && apt-get install -y python3-pip jq git software-properies-common \
    && pip3 install awscli \
    && apt-add-repository ppa:ansible/ansible \
    && apt-get install -y ansible