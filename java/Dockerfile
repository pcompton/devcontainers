FROM philcompton/devcontainer-base:latest

USER root

ENV JAVA_VERSION="21+35"
ENV JAVA_ALT_VERSION="21_35"
ENV PATH="${PATH}:/opt/jdk-${JAVA_VERSION}/bin"
ENV JAVA_HOME="/opt/jdk-${JAVA_VERSION}/"
ENV JAVA_SHA256="82f64c53acaa045370d6762ebd7441b74e6fda14b464d54d1ff8ca941ec069e6"

RUN wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-${JAVA_VERSION}/OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && echo "${JAVA_SHA256} OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && rm OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz

USER vscode