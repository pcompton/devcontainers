FROM archlinux/archlinux:base-devel

ENV BUILD_DATE 20230920

RUN pacman -Syu --noconfirm \
    && pacman -S --noconfirm curl git libicu libuser unzip wget zsh  \
    && pacman -Scc --noconfirm

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

