FROM philcompton/dev-base:latest

USER root

RUN dnf install gcc gcc-gfortran libRmath libRmath-devel python3-devel python3-pip python3-wheel R-base R-inline -y \
    && dnf clean all -y 

USER vscode

RUN pip3 install -U radian \
    && mkdir -p ~/R/x86_64-redhat-linux-gnu-library/4.4 \
    && R -e "install.packages(c('languageserver','tidyverse','httpgd'), repos = 'https://archive.linux.duke.edu/cran/')"
