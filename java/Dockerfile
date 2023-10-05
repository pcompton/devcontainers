FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -Syu --noconfirm \
    && pacman -S --noconfirm gradle jdk-openjdk openjdk-doc openjdk-src  \
    && pacman -Scc --noconfirm

USER vscode