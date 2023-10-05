FROM philcompton/devcontainer-go:latest

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="20.8.0"
ENV NODE_SHA256="66056a2acc368db142b8a9258d0539e18538ae832b3ccb316671b0d35cb7c72c"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
