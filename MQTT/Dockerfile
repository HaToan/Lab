FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -qy --no-install-recommends mosquitto \
        build-essential \
        git \
        mosquitto-dev \
        libmosquitto-dev \
        openssl \
        libssl-dev \
        ca-certificates

RUN apt-get purge -y --auto-remove  build-essential \
        git \
        mosquitto-dev \
        libmosquitto-dev \
        openssl \
        libssl-dev \
        ca-certificates

RUN apt-get  clean

# Copy rootfs
COPY rootfs /
COPY entrypoint.sh /
RUN chmod +x /entrypoint.sh

WORKDIR /

 CMD ["/entrypoint.sh"]