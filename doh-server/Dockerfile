# https://github.com/jedisct1/doh-server

FROM ubuntu:20.10

RUN apt update \
    && apt install wget -y \
    && wget --no-check-certificate https://github.com/jedisct1/doh-server/releases/download/0.9.0/doh-proxy_0.9.0_amd64.deb \
    && dpkg -i doh-proxy_0.9.0_amd64.deb

ENTRYPOINT ["/usr/bin/doh-proxy"]
