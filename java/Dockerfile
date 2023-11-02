FROM philcompton/devcontainer-base:latest

USER root

ENV JAVA_VERSION="21.0.1+12"
ENV JAVA_ALT_VERSION="21.0.1_12"
ENV PATH="${PATH}:/opt/jdk-${JAVA_VERSION}/bin"
ENV JAVA_HOME="/opt/jdk-${JAVA_VERSION}/"
ENV JAVA_SHA256="1a6fa8abda4c5caed915cfbeeb176e7fbd12eb6b222f26e290ee45808b529aa1"

RUN wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-${JAVA_VERSION}/OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && echo "${JAVA_SHA256} OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && rm OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz

USER vscode