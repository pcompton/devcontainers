FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y python3-autopep8 python3-devel python3-pip python3-prompt-toolkit python3-setuptools \ 
    python3-virtualenv python3-wheel  \
    && dnf clean all -y

USER vscode