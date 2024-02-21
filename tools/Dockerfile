ARG BASE_IMAGE
ARG SYFT_VER
ARG GRYPE_VER

FROM anchore/syft:${SYFT_VER:-v0.92.0} as syft

FROM anchore/grype:${GRYPE_VER:-v0.69.1} as grype

# ----------------------------------------------

FROM ${BASE_IMAGE:-alpine:3.18}

ARG GIT_VERSION=1.0.0

LABEL org.opencontainers.image.maintainer="Denis Rendler <connect@rendler.net>" \
    org.opencontainers.image.version=$GIT_VERSION \
    org.opencontainers.image.description="Image containing security scanning tools" \
    org.opencontainers.image.source="https://github.dev/httpsec-eu/gitlab-security-components" \
    org.opencontainers.image.url="https://www.denis.rendler.me" \
    org.opencontainers.image.authors="Denis Rendler"

COPY --from=syft /syft /usr/local/bin/syft
COPY --from=grype /grype /usr/local/bin/grype

RUN apk update && apk upgrade -f -l --no-interactive

CMD ["/bin/sh"]
