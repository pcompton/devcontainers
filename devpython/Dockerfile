FROM python:3.11-bullseye

ENV BUILD_DATE 20230604

RUN apt update  \
    && apt upgrade -y \
    && apt install -y bat curl exa git jq libicu-dev libuser make ripgrep unzip wget zsh  \
    && apt clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

