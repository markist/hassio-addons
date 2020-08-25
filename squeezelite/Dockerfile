ARG BUILD_FROM=hassioaddons/ubuntu-base:5.2.1
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Set correct environment variables
ENV DEBIAN_FRONTEND="noninteractive"
ENV LC_ALL="C.UTF-8" 
ENV LANG="en_US.UTF-8" 
ENV LANGUAGE="en_US.UTF-8" 

# Use baseimage-docker's init system.
#CMD ["/sbin/my_init"]

# Upgrading the operating system inside the container
RUN apt-get update && apt-get upgrade -y -o Dpkg::Options::="--force-confold"

# Install Squeezelite
RUN apt-get -qq -y update && \
    apt-get -qq -y install alsa-base alsa-utils libasound2-data libasound2-dev libasound2-plugins libasound2 curl && \
	curl -o squeezelite.tar.gz -L https://sourceforge.net/projects/lmsclients/files/squeezelite/linux/squeezelite-1.9.7.1270-x86_64.tar.gz/download && \
	tar -xvzf squeezelite.tar.gz && \
    mv squeezelite /usr/bin && \
    chmod +x /usr/bin/squeezelite && \
	rm -f LICENSE.txt && \
	rm -f squeezelite.tar.gz

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Copy root filesystem
COPY rootfs /

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

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
