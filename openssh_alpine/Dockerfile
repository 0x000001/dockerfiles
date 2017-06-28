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
    && touch entrypoint.sh    
RUN echo "#!/bin/sh" >> /entrypoint.sh
RUN echo "cd /root/.ssh" >>/entrypoint.sh
RUN echo "touch authorized_keys"
RUN echo "echo  \"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDvWmXctrml4SfnrmJJFB4C7BR83u0yiBbe6k18dbl7W3tx5UQ5KcEqXhrYg1LTQVNsvdcw3Gj+sr5qNAR0ZGSV+RhD5iasnUGkNJ4dVxYNMzMXZwmVbg5YZtl55xsiwwdcriiAl01ibJ7UM8Be4GaXa+/eTTKKKNUmjMoZT1SMjRjwIqLd72W1VJKk17gqfWFi4SDT05hwH/poj3qP70QEfvi6IiNlCmVzTWQgjQJkMOtIi8zrPIoWRFLGUSJkLVCSe7Nx5H1EnUHGzQ643Wiv4KHh8ipuP70xtSaD15L/678FB8PxnAcYsnQUi5qpAvjDY4YcBQEic+NQbz1kQmPB nullun@null\"  >> authorized_keys" >>/entrypoint.sh
RUN echo "ssh-keygen -A"  >>/entrypoint.sh
RUN echo "exec /usr/sbin/sshd -D \"$@\" -p 2222" >> /entrypoint.sh

WORKDIR /root

EXPOSE 2222

ENTRYPOINT ["/entrypoint.sh"]
