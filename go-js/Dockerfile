FROM philcompton/devcontainer-go:latest

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.7.0"
ENV NODE_SHA256="a4251c24c6bf6d3bdee4521ca294bc0897a6c466137e02caa2521af5d456f55e"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
