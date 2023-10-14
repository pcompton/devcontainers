FROM philcompton/devcontainer-go:latest

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.8.1"
ENV NODE_SHA256="44096f6276cf735f3b25f47ffaaa1629b0abad4d9932c3a77d9dcdc743a3ff92"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
