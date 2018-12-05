FROM node:10-alpine

ENV CERTS="djer djsn djte djgc djdi djsc"
RUN apk update && \
    apk add --no-cache ca-certificates python alpine-sdk && \
    for cert in $CERTS; do wget -q -P /usr/local/share/ca-certificates http://pki.dowjones.com/ca/${cert}-pem.crt; done && \
    update-ca-certificates && \
    npm config set cafile /etc/ssl/certs/ca-certificates.crt && \
    npm install --global add pm2 typescript ts-node nyc mocha && \
    pm2 install typescript && \
    npm cache clean --force && \
    rm -rf /var/cache/apk/*
