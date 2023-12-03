FROM philcompton/dev-base:20231203

USER root

RUN dnf install -y lldb llvm && dnf clean all -y

USER vscode

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | bash -s -- -y \
    && source $HOME/.cargo/env \
    && rustup component add rust-analysis rust-src \
    && rustup component add rustfmt clippy

