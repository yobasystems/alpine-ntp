FROM yobasystems/alpine:3.19.0-aarch64

ARG BUILD_DATE
ARG VCS_REF

LABEL maintainer="Dominic Taylor <dominic@yoba.systems>" \
    architecture="arm64v8/aarch64" \
    chrony-version="4.5" \
    alpine-version="3.19.0" \
    build="21-Jan-2024" \
    org.opencontainers.image.title="alpine-ntp" \
    org.opencontainers.image.description="Chrony Docker image running on Alpine Linux" \
    org.opencontainers.image.authors="Dominic Taylor <dominic@yoba.systems>" \
    org.opencontainers.image.vendor="Yoba Systems" \
    org.opencontainers.image.version="v4.5" \
    org.opencontainers.image.url="https://hub.docker.com/r/yobasystems/alpine-ntp/" \
    org.opencontainers.image.source="https://github.com/yobasystems/alpine-ntp" \
    org.opencontainers.image.revision=$VCS_REF \
    org.opencontainers.image.created=$BUILD_DATE

RUN apk add --no-cache chrony

ADD files/run.sh /opt/startup.sh

EXPOSE 123/udp

HEALTHCHECK CMD chronyc tracking || exit 1

ENTRYPOINT [ "/bin/sh", "/opt/startup.sh" ]
