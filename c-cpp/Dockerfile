FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -S cmake gdb gef ltrace nasm --noconfirm \
    && pacman -Scc --noconfirm

USER vscode


