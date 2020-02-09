FROM alpine:3.10.2

# Create arguments to be used for generating non-root user
ARG USERNAME=dev

# Update, add basic packages, and create a non-root user
# Non-root user will have sudo privileges
RUN apk update  \
    && apk add gnupg sudo nodejs-npm python python-dev py-pip \
    && addgroup -S $USERNAME \
    && adduser -D -S $USERNAME -G $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER dev