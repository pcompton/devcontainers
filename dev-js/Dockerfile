FROM philcompton/dev-base:20231122

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.9.0"
ENV NODE_SHA256="9033989810bf86220ae46b1381bdcdc6c83a0294869ba2ad39e1061f1e69217a"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
