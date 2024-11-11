FROM philcompton/dev-base:20241111

ENV GOPATH="/home/vscode/go"
ENV GOROOT="/opt/go"
ENV PATH="${PATH}:${GOROOT}/bin:${GOPATH}/bin"
ENV GO_VERSION="1.23.3"
ENV GO_SHA256="a0afb9744c00648bafb1b90b4aba5bdb86f424f02f9275399ce0c20b93a2c3a8"

USER root

RUN dnf upgrade -y && dnf install -y bcc bcc-devel bcc-tools binutils bpftool clang cmake gcc libbpf \
    libbpf-devel libbpf-tools libtool lldb llvm kernel-devel python3-bcc && dnf clean all -y

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