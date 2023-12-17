FROM philcompton/dev-base:20231217

USER root

RUN dnf upgrade -y && dnf install -y cmake gcc gcc-c++ gdb libtool make nasm && dnf clean all -y


USER vscode


