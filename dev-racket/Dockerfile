FROM philcompton/dev-base:20240107

USER root

ENV PATH="${PATH}:/opt/racket/bin"
ENV RACKET_VERSION="8.11.1"
ENV RACKET_SHA256="0b4b22ce67d4f8a529a16c27e445150859c90671c9582daf00b4df053e1f3a75"

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
