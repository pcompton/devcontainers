FROM philcompton/dev-base:latest

USER root

ENV PATH="${PATH}:/opt/racket/bin"
ENV RACKET_VERSION="8.16"
ENV RACKET_SHA256="112e130000ab0b3cdddf907de2a357502a0643123af568fb20d4f118c96a4b8a"

RUN wget https://download.racket-lang.org/releases/${RACKET_VERSION}/installers/racket-minimal-${RACKET_VERSION}-x86_64-linux-cs.tgz \
    && echo "${RACKET_SHA256} racket-minimal-${RACKET_VERSION}-x86_64-linux-cs.tgz" | sha256sum -c - \
    && tar -C /opt/ -xzf racket-minimal-${RACKET_VERSION}-x86_64-linux-cs.tgz \
    && rm racket-minimal-${RACKET_VERSION}-x86_64-linux-cs.tgz

ENV SSL_CERT_FILE="/etc/ssl/certs/ca-certificates.crt"
ENV SSL_CERT_DIR="/etc/ssl/certs"

RUN raco setup
RUN raco pkg config --set catalogs \
    "https://download.racket-lang.org/releases/${RACKET_VERSION}/catalog/" \
    "https://pkg-build.racket-lang.org/server/built/catalog/" \
    "https://pkgs.racket-lang.org" \
    "https://planet-compats.racket-lang.org"

USER vscode

RUN raco pkg install --auto racket-langserver
