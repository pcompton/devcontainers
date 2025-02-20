FROM philcompton/dev-base:20250220

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="22.14.0"
ENV NODE_SHA256="69b09dba5c8dcb05c4e4273a4340db1005abeafe3927efda2bc5b249e80437ec"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
