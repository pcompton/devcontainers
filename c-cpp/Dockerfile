FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y clang cmake gcc-c++ gdb libtool lldb llvm ltrace && dnf clean all -y


USER vscode


