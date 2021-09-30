FROM ubuntu:20.04

ARG THIS_ARCH_GO=amd64
ARG FRP_VER=0.37.1

RUN \
  apt-get update && \
  apt-get install -y wget tar && \
  mkdir -p /tmp/frp && \
  wget -O /tmp/frp/frps.tar.gz --no-check-certificate https://github.com/fatedier/frp/releases/download/v${FRP_VER}/frp_${FRP_VER}_linux_${THIS_ARCH_GO}.tar.gz && \
  tar -xf /tmp/frp/frps.tar.gz -C /tmp/frp && \
  mv /tmp/frp/frp_${FRP_VER}_linux_${THIS_ARCH_GO}/frps /usr/bin/ && \
  chmod +x /usr/bin/frps && \
  apt-get clean && \
  rm -rf /tmp/frp && \
  mkdir /frp

WORKDIR /frp
ENTRYPOINT ["/usr/bin/frps"]