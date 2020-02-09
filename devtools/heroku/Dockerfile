FROM docker:latest

RUN apk update - \
    && apk add bash jq git curl nodejs-npm \
    && curl https://cli-assets.heroku.com/install.sh | sh