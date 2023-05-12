FROM fedora:38

ENV BUILD_DATE 20230512

RUN dnf update -y \
    && dnf install -y bat curl exa gcc git iputils jq libicu libuser make ripgrep unzip wget xz zsh  \
    && dnf clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

