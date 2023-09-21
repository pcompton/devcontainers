FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -S flake8 ipython jupyter-notebook jupyter-server python python-jedi \
    python-matplotlib python-pip python-pytest python-setuptools python-virtualenv \
    python-wheel --noconfirm \
    && pacman -Scc --noconfirm

USER vscode