FROM philcompton/devcontainer-base:latest

USER root

ENV RACKET_INSTALLER_URL https://download.racket-lang.org/releases/8.9/installers/racket-8.9-x86_64-linux-cs.sh
ENV RACKET_VERSION 8.9

RUN curl --retry 5 -Ls "${RACKET_INSTALLER_URL}" > racket-install.sh \
    && echo "yes\n1\n" | sh racket-install.sh --create-dir --unix-style --dest /usr/ \
    && rm racket-install.sh

ENV SSL_CERT_FILE="/etc/ssl/certs/ca-certificates.crt"
ENV SSL_CERT_DIR="/etc/ssl/certs"

RUN raco setup
RUN raco pkg config --set catalogs \
    "https://download.racket-lang.org/releases/${RACKET_VERSION}/catalog/" \
    "https://pkg-build.racket-lang.org/server/built/catalog/" \
    "https://pkgs.racket-lang.org" \
    "https://planet-compats.racket-lang.org"

USER vscode

RUN raco pkg install chk chk-lib chk-doc html-parsing mcfly overeasy racket-langserver
