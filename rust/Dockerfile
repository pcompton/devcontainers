FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -S clang lldb llvm --noconfirm \
    && pacman -Scc --noconfirm

USER vscode

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | bash -s -- -y \
    && source $HOME/.cargo/env \
    && rustup component add rust-analysis rust-src \
    && rustup component add rustfmt clippy

