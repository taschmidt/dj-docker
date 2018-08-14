FROM node:8.11.3-alpine

RUN apk update && apk add ca-certificates yarn python

# install DJ certs
ENV CERTS="djer djsn djte djgc djdi djsc"
RUN for cert in $CERTS; do wget -q -P /usr/local/share/ca-certificates http://pki.dowjones.com/ca/${cert}-pem.crt; done
RUN ls -la /usr/local/share/ca-certificates
RUN update-ca-certificates
RUN yarn config set cafile /etc/ssl/certs/ca-certificates.crt

# check yarn version
RUN yarn --version

# install other globals
RUN yarn global add serverless nyc mocha
