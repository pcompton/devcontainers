FROM debian:sid

ENV BUILD_DATE 20231102

RUN apt update -y \
    && apt install -y curl gcc git libicu72 libuser make ripgrep unzip wget xz-utils zsh  \
    && apt clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

