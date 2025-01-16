FROM philcompton/dev-base:20250116

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="22.13.0"
ENV NODE_SHA256="3ff0d57063c33313d73d0bdcebc4c778ad6be948234584694a042c6fe57164f6"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
