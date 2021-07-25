from debian:buster-slim

RUN apt-get update
RUN apt-get install squeezelite -y
RUN rm -rf /var/lib/apt/lists/*

COPY run-squeezelite.sh /run-squeezelite.sh
RUN chmod u+x /run-squeezelite.sh

ENV SQUEEZELITE_AUDIO_DEVICE front:CARD=HM,DEV=0
ENV SQUEEZELITE_NAME SqueezeLiteBad
ENV SQUEEZELITE_TIMEOUT 2
ENV SQUEEZELITE_DELAY 500

ENV STARTUP_DELAY_SEC 0

ENV SQUEEZELITE_SPECIFY_SERVER no
ENV SQUEEZELITE_SERVER_PORT server:3483


# Labels
LABEL \
    io.hass.name="Squeezelite" \
    io.hass.description="Standalone Squeezelite client" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Lars Werner <lars@werner.no>" \
    org.opencontainers.image.title="Squeezelite" \
    org.opencontainers.image.description="Standalone Squeezelite client" \
    org.opencontainers.image.vendor="Lars Werner" \
    org.opencontainers.image.authors="Lars Werner <lars@werner.no>" \
    org.opencontainers.image.licenses="APACHE" \
    org.opencontainers.image.url="https://lars.werner.no/" \
    org.opencontainers.image.source="https://github.com/large/hassio-addons" \
    org.opencontainers.image.documentation="https://github.com/large/hassio-addons/blob/master/squeezelite/DOCS.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}


ENTRYPOINT ["/run-squeezelite.sh"]