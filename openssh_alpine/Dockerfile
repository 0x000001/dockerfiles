#
# Dockerfile for openssh
#

FROM alpine
MAINTAINER null

RUN set -xe \
    && apk add --no-cache openssh \
    && mkdir -p 700 /root/.ssh \
    && mv /etc/ssh /root/.ssh/ssh \
    && ln -s /root/.ssh/ssh /etc/ssh \
    && curl http://github.com/0x000001/dockerfiles/blob/master/openssh_alpine/entrypoint.sh    /entrypoint.sh


WORKDIR /root

EXPOSE 2222

ENTRYPOINT ["/entrypoint.sh"]
