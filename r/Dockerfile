FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y libRmath libRmath-devel python3-pip R-core R-core-devel R-R6  \
    && dnf clean all -y

USER vscode

RUN pip3 install -U radian \
    && mkdir -p ~/R/x86_64-redhat-linux-gnu-library/4.2 \
    && R -e "install.packages(c('languageserver','tidyverse'), repos = 'https://archive.linux.duke.edu/cran/')"
