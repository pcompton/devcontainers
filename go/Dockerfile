FROM philcompton/devcontainer-base:20231118

USER root

ENV PATH="${PATH}:/opt/go/bin"
ENV GOPATH="/home/vscode/go"
ENV GOROOT="/opt/go"
ENV GO_VERSION="1.21.3"
ENV GO_SHA256="1241381b2843fae5a9707eec1f8fb2ef94d827990582c7c7c32f5bdfbfd420c8"

RUN wget https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz \
    && echo "${GO_SHA256} go${GO_VERSION}.linux-amd64.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf go${GO_VERSION}.linux-amd64.tar.gz \
    && rm go${GO_VERSION}.linux-amd64.tar.gz

USER vscode

RUN go install golang.org/x/tools/gopls@latest \
    && go install golang.org/x/tools/cmd/goimports@latest \
    && go install golang.org/x/lint/golint@latest \
    && go install github.com/go-delve/delve/cmd/dlv@latest \
    && go install honnef.co/go/tools/cmd/staticcheck@latest \
    && go install github.com/fatih/gomodifytags@latest \
    && go install github.com/josharian/impl@latest
