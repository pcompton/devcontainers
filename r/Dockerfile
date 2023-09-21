FROM philcompton/devcontainer-base:latest

USER root

RUN pacman -S gcc-fortran python python-pip r --noconfirm \
    && pacman -Scc --noconfirm

RUN R -e "install.packages(c('httpg', 'languageserver','tidyverse'), repos = 'https://archive.linux.duke.edu/cran/')"

USER vscode

RUN pip3 install -U radian 