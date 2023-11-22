FROM philcompton/dev-base:20231122

USER root

RUN apt update -y \
    && apt install gfortran python3-pip r-base -y \
    && apt clean all -y \
    && && R -e "install.packages(c('languageserver','tidyverse'), repos = 'https://archive.linux.duke.edu/cran/')"

USER vscode

RUN pip install -U radian \