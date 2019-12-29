FROM alpine:3.10.2

ARG VERSION=1.32.3
RUN apk update \
    && apk add curl tar \
    && curl -OL https://github.com/digitalocean/doctl/releases/download/v${VERSION}/doctl-${VERSION}-linux-amd64.tar.gz \
    && tar xf doctl-${VERSION}-linux-amd64.tar.gz \
    && mv doctl /usr/local/bin \
    && rm -rf doctl-${VERSION}-linux-amd64.tar.gz