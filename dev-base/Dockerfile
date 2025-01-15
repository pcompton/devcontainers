FROM fedora:41

ENV BUILD_DATE="20250115"

RUN dnf upgrade -y \
    && dnf install -y curl gawk git jq libuser make ripgrep sed unzip wget xz \
    && dnf clean all -y

RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode -s /usr/bin/zsh

USER vscode
