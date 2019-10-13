FROM docker:latest

# Install python, awscli, and ansible
# Additional packages needed to install all packages required for ansible and aws
RUN apk update \ 
    && apk add gcc libc-dev musl-dev python3 python3-dev py3-pip libffi-dev jq git vim openssl-dev \
    && pip3 install --upgrade pip \
    && pip3 install awscli boto boto3 'ansible==2.8.5.0'