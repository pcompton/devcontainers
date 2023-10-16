FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y gcc-fortran libRmath libRmath-devel python3-pip R-core R-core-devel R-R6  \
    && dnf clean all -y

USER vscode

RUN  mkdir -p ~/R/x86_64-redhat-linux-gnu-library/4.3 \
    && R -e "install.packages(c('languageserver','tidyverse'), repos = 'https://archive.linux.duke.edu/cran/')"

# pip3 install -U radian \