FROM archlinux/archlinux:base-devel

ENV BUILD_DATE 20230910

RUN pacman -Syu --noconfirm \
    && pacman -S --noconfirm curl gcc git iputils libicu libuser make unzip wget xz zsh  \
    && dnf clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

