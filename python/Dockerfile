FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y python3-autopep8 python3-devel python3-pip python3-prompt-toolkit python3-setuptools \ 
    python3-virtualenv python3-wheel  \
    python3-jupyter-core python3-jupyter-console python3-jupyter-client python3-ipykernel python3-ipywidgets \
    python3-nbconvert python3-nbformat python3-numpy python3-numpy-doc python3-pandas \
    python3-matplotlib python3-matplotlib-data python3-matplotlib-doc \
    && dnf clean all -y

USER vscode