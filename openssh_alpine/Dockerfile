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
    && apk add --no-cache curl \
    && curl https://raw.githubusercontent.com/0x000001/dockerfiles/master/openssh_alpine/entrypoint.sh    >>/entrypoint.sh \
    &&chmod +x /entrypoint.sh


WORKDIR /root

EXPOSE 2222

ENTRYPOINT ["/entrypoint.sh"]
