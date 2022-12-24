FROM ubuntu:22.04

RUN apt-get update \
    && apt-get install wget -y \
    && wget --no-check-certificate https://github.com/DNSCrypt/doh-server/releases/download/0.9.4/doh-proxy_0.9.4_amd64.deb \
    && dpkg -i doh-proxy_0.9.4_amd64.deb \
    && rm -f doh-proxy_0.9.4_amd64.deb

ENTRYPOINT ["/usr/bin/doh-proxy"]