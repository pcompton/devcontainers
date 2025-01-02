FROM philcompton/dev-base:20250102

USER root

ENV PATH="${PATH}:/opt/node/bin"
ENV NODE_VERSION="22.12.0"
ENV NODE_SHA256="22982235e1b71fa8850f82edd09cdae7e3f32df1764a9ec298c72d25ef2c164f"

RUN wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz \
    && echo "${NODE_SHA256} node-v${NODE_VERSION}-linux-x64.tar.xz" | sha256sum -c - \
    && tar -C /opt/ -xf node-v${NODE_VERSION}-linux-x64.tar.xz \
    && mv /opt/node-v${NODE_VERSION}-linux-x64 /opt/node \
    && rm node-v${NODE_VERSION}-linux-x64.tar.xz

RUN npm install -g typescript \
    && npm install -g @angular/cli

USER vscode
