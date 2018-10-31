FROM node:8.11.4-alpine

ENV CERTS="djer djsn djte djgc djdi djsc"
RUN apk update && \
    apk add --no-cache --virtual .deps ca-certificates yarn python alpine-sdk bash && \
    for cert in $CERTS; do wget -q -P /usr/local/share/ca-certificates http://pki.dowjones.com/ca/${cert}-pem.crt; done && \
    ls -la /usr/local/share/ca-certificates && \
    update-ca-certificates && \
    yarn config set cafile /etc/ssl/certs/ca-certificates.crt && \
    yarn --version && \
    yarn global add pm2 typescript ts-node nyc mocha && \
    apk del .deps
