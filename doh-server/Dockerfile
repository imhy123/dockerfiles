FROM debian:10

RUN apt update \
    && apt install wget -y \
    && wget --no-check-certificate https://cdn.spirithy.com/software/doh-proxy_0.3.8_amd64.deb \
    && dpkg -i doh-proxy_0.3.8_amd64.deb

ENTRYPOINT ["/usr/bin/doh-proxy"]