FROM philcompton/dev-base:20240128

USER root

RUN dnf upgrade -y && dnf install -y cmake gcc gcc-c++ gdb libtool make nasm && dnf clean all -y


USER vscode


