FROM philcompton/devcontainer-base:latest

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="18.16.0"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

USER vscode

RUN npm install -g typescript \
    && npm install -g @angular/cli

