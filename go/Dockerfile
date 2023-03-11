FROM fedora:37

ENV PATH="${PATH}:/opt/go/bin"
ENV GOPATH="/home/vscode/go"
ENV GOROOT="/opt/go"
ENV GO_VERSION="1.20.2"

RUN dnf update -y \
    && dnf install -y curl dotnet gcc git libicu make unzip wget  \
    && dnf clean all -y

RUN wget https://go.dev/dl/go${GO_VERSION}.linux-amd64.tar.gz \
    && tar -C /opt/ -xzf go${GO_VERSION}.linux-amd64.tar.gz \
    && rm go${GO_VERSION}.linux-amd64.tar.gz

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode 

USER vscode

RUN go install golang.org/x/tools/gopls@latest \
    && go install golang.org/x/tools/cmd/goimports@latest \
    && go install golang.org/x/lint/golint@latest \
    && go install github.com/go-delve/delve/cmd/dlv@latest \
    && go install honnef.co/go/tools/cmd/staticcheck@latest \
    && go install github.com/fatih/gomodifytags@latest \
    && go install github.com/josharian/impl@latest
