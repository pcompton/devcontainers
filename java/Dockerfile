FROM philcompton/devcontainer-base:latest

USER root

RUN dnf install -y java-17-openjdk java-17-openjdk-devel java-17-openjdk-headless java-17-openjdk-javadoc \
    java-17-openjdk-jmods java-17-openjdk-src maven maven-openjdk17 maven-local-openjdk17 \
    && dnf clean all -y

USER vscode