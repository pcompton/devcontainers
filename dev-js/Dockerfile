FROM philcompton/dev-base:20241108

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="22.11.0"
ENV NODE_SHA256="83bf07dd343002a26211cf1fcd46a9d9534219aad42ee02847816940bf610a72"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
