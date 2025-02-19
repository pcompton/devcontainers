FROM philcompton/dev-base:20250219

USER root

ENV JAVA_VERSION="21.0.6+7"
ENV JAVA_ALT_VERSION="21.0.6_7"
ENV PATH="${PATH}:/opt/jdk-${JAVA_VERSION}/bin"
ENV JAVA_HOME="/opt/jdk-${JAVA_VERSION}/"
ENV JAVA_SHA256="a2650fba422283fbed20d936ce5d2a52906a5414ec17b2f7676dddb87201dbae"

RUN wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-${JAVA_VERSION}/OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && echo "${JAVA_SHA256} OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && rm OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz

USER vscode