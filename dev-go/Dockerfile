FROM philcompton/dev-base:latest

USER root

ENV GOPATH="/home/vscode/go"
ENV GOROOT="/opt/go"
ENV PATH="${PATH}:${GOROOT}/bin:${GOPATH}/bin"
ENV GO_VERSION="1.24.2"
ENV GO_SHA256="68097bd680839cbc9d464a0edce4f7c333975e27a90246890e9f1078c7e702ad"

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
    && go install github.com/josharian/impl@latest \
    && go install golang.org/x/tools/cmd/deadcode@latest
