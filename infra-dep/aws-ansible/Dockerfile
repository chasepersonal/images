FROM debian:stretch-slim

# Install python with pip, jq, git, awscli, ansible
RUN apt-get update \ 
    && apt-get install -y python3-pip jq git software-properties-common \
    && pip3 install awscli boto boto3 'ansible==2.8.5.0'