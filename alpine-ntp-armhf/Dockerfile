FROM yobasystems/alpine:3.23.0-armhf

ARG BUILD_DATE
ARG VCS_REF

LABEL maintainer="Dominic Taylor <dominic@yoba.systems>" \
    architecture="arm32v7/armhf" \
    chrony-version="4.8.0" \
    alpine-version="3.23.0" \
    build="04-Dec-2025" \
    org.opencontainers.image.title="alpine-ntp" \
    org.opencontainers.image.description="Chrony Container image running on Alpine Linux" \
    org.opencontainers.image.authors="Dominic Taylor <dominic@yoba.systems>" \
    org.opencontainers.image.vendor="Yoba Systems" \
    org.opencontainers.image.version="4.8.0" \
    org.opencontainers.image.url="https://hub.docker.com/r/yobasystems/alpine-ntp/" \
    org.opencontainers.image.source="https://github.com/yobasystems/alpine-ntp" \
    org.opencontainers.image.base.name="docker.io/yobasystems/alpine:3.23.0" \
    org.opencontainers.image.revision=$VCS_REF \
    org.opencontainers.image.created=$BUILD_DATE

RUN apk add --no-cache chrony

ADD files/run.sh /opt/startup.sh

EXPOSE 123/udp

HEALTHCHECK CMD chronyc tracking || exit 1

ENTRYPOINT [ "/bin/sh", "/opt/startup.sh" ]
