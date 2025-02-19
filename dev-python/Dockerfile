FROM philcompton/dev-base:20250219

USER root

RUN dnf update -y \
    && dnf install python3 python3-autopep8 python3-flake8 python3-pip python3-virtualenv -y \
    && dnf clean all -y 

USER vscode