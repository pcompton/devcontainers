FROM philcompton/dev-java:20231228

USER root

ENV PATH="${PATH}:/opt/graalvm-jdk-21.0.1+12.1/bin"


RUN wget https://download.oracle.com/graalvm/21/latest/graalvm-jdk-21_linux-x64_bin.tar.gz \
    && tar -C /opt/ -xzf graalvm-jdk-21_linux-x64_bin.tar.gz \
    && rm graalvm-jdk-21_linux-x64_bin.tar.gz

USER vscode