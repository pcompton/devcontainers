FROM philcompton/dev-base:latest

USER root

RUN dnf upgrade -y && dnf install -y swi-prolog-core swi-prolog-core-packages swi-prolog-doc swi-prolog-nox  && dnf clean all -y


USER vscode
