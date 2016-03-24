FROM microsoft/aspnet:1.0.0-rc1-update1-coreclr

ADD ./djca-v3.pem /usr/local/share/ca-certificates/djca-v3.crt
ADD ./NuGet.config /root/.config/NuGet/NuGet.config

RUN update-ca-certificates --fresh && \
    apt-get install curl && \
    curl -sL https://deb.nodesource.com/setup_4.x | bash - && \
    apt-get install -y nodejs && \
    npm set progress=false && \
    npm install -g gulp@3.9.1 && \
    npm install -g bower@1.7.7 && \
    npm config --global set registry http://registry.npm.wsjfdev.dowjones.net/
