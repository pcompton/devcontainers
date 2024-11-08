FROM philcompton/dev-base:20241108

USER root

RUN dnf upgrade -y && dnf install -y binutils cmake gcc gcc-c++ gdb libtool nasm && dnf clean all -y


USER vscode
