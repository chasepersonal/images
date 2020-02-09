# Pull full sdk image
FROM google/cloud-sdk:latest

# Install git, wget, vim, and helm for development/troubleshooting
RUN apt-get update -y \
    && apt-get upgrade -y \
    && apt-get install git wget vim -y \
    && curl -L https://git.io/get_helm.sh | bash