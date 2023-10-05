FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -S clang cmake gdb gef lldb llvm ltrace nasm --noconfirm \
    && pacman -Scc --noconfirm

USER vscode


