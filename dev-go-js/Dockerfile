FROM philcompton/dev-go:20240107

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.10.0"
ENV NODE_SHA256="3fe4ec5d70c8b4ffc1461dec83ab23fc70124e137c4cbbe1ccc9d6ae6ec04a7d"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
