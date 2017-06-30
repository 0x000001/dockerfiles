FROM alpine:latest
MAINTAINER nullun 

RUN apk update && apk add py-pip && pip install shadowsocks

ENTRYPOINT ["/usr/bin/ssserver"]
