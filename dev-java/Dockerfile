FROM philcompton/dev-base:20240902

USER root

ENV JAVA_VERSION="21.0.4+7"
ENV JAVA_ALT_VERSION="21.0.4_7"
ENV PATH="${PATH}:/opt/jdk-${JAVA_VERSION}/bin"
ENV JAVA_HOME="/opt/jdk-${JAVA_VERSION}/"
ENV JAVA_SHA256="51fb4d03a4429c39d397d3a03a779077159317616550e4e71624c9843083e7b9"

RUN wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-${JAVA_VERSION}/OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && echo "${JAVA_SHA256} OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && rm OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz

USER vscode