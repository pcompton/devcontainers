FROM philcompton/dev-base:20231126

USER root

RUN dnf install gfortran python3-pip r-base -y \
    && dnf clean all -y \
    && R -e "install.packages(c('languageserver','tidyverse'), repos = 'https://archive.linux.duke.edu/cran/')"

USER vscode

RUN pip install -U radian \