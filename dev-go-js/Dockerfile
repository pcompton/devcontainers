FROM philcompton/dev-go:20240121

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.11.0"
ENV NODE_SHA256="822780369d0ea309e7d218e41debbd1a03f8cdf354ebf8a4420e89f39cc2e612"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
