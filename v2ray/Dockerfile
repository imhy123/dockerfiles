ARG THIS_ARCH_ALT=amd64
FROM multiarch/alpine:${THIS_ARCH_ALT}-edge

ARG THIS_ARCH_GO=linux-64

ENV V2RAY_VER=v4.18.0

RUN apk --no-cache add wget unzip tzdata \
  && cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && wget --no-check-certificate https://github.com/v2ray/v2ray-core/releases/download/${V2RAY_VER}/v2ray-${THIS_ARCH_GO}.zip \
  && unzip v2ray-${THIS_ARCH_GO}.zip -d /tmp/v2ray \
  && mkdir -p /usr/bin/vy \
  && mv /tmp/v2ray/v2ray /usr/bin/vy/vy \
  && mv /tmp/v2ray/v2ctl /usr/bin/vy/ \
  && mv /tmp/v2ray/geoip.dat /usr/bin/vy/ \
  && mv /tmp/v2ray/geosite.dat /usr/bin/vy/ \
  && chmod +x /usr/bin/vy/vy \
  && chmod +x /usr/bin/vy/v2ctl \
  && rm -f v2ray-${THIS_ARCH_GO}.zip \
  && rm -rf /tmp/v2ray \
  && apk del --purge wget unzip \
  && mkdir /vy

WORKDIR /vy
ENTRYPOINT ["/usr/bin/vy/vy"]