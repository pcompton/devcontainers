FROM philcompton/dev-base:20240128

USER root

ENV JAVA_VERSION="21.0.2+13"
ENV JAVA_ALT_VERSION="21.0.2_13"
ENV PATH="${PATH}:/opt/jdk-${JAVA_VERSION}/bin"
ENV JAVA_HOME="/opt/jdk-${JAVA_VERSION}/"
ENV JAVA_SHA256="454bebb2c9fe48d981341461ffb6bf1017c7b7c6e15c6b0c29b959194ba3aaa5"

RUN wget https://github.com/adoptium/temurin21-binaries/releases/download/jdk-${JAVA_VERSION}/OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && echo "${JAVA_SHA256} OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz" | sha256sum -c - \
    && tar -C /opt/ -xzf OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz \
    && rm OpenJDK21U-jdk_x64_linux_hotspot_${JAVA_ALT_VERSION}.tar.gz

USER vscode