FROM philcompton/dev-go:20250220

USER root

RUN dnf upgrade -y && dnf install -y bcc bcc-devel bcc-tools binutils bpftool clang cmake gcc libbpf \
    libbpf-devel libbpf-tools libtool lldb llvm kernel-devel python3-bcc && dnf clean all -y

USER vscode
