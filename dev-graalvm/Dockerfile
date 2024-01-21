FROM philcompton/dev-java:20240121

USER root

ENV PATH="${PATH}:/opt/graalvm-jdk-21.0.2+13.1/bin"
ENV GRAALVM_SHA256="ee6286773c659afeefdf2f989a133e7a631c60897f2263ac183794ee1d6438f4"


RUN wget https://download.oracle.com/graalvm/21/latest/graalvm-jdk-21_linux-x64_bin.tar.gz \
    && echo "${GRAALVM_SHA256} graalvm-jdk-21_linux-x64_bin.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf graalvm-jdk-21_linux-x64_bin.tar.gz \
    && rm graalvm-jdk-21_linux-x64_bin.tar.gz

USER vscode