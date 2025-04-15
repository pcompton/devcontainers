FROM registry.fedoraproject.org/fedora:42

ENV BUILD_DATE="20250415"

RUN dnf upgrade -y \
    && dnf install -y bat curl gawk git jq just libuser make ripgrep rpmdevtools sed unzip wget xz zsh \
    && dnf clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode

RUN sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

COPY ./zshrc /home/vscode/.zshrc

RUN rpmdev-setuptree