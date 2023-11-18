FROM philcompton/devcontainer-base:20231118

USER root

RUN apt update -y \
    && apt install python3 python3-autopep8 python3-flake8 python3-pip python3-virtualenv -y \
    && apt clean all -y 

USER vscode