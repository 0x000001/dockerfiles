# FROM ubuntu:14.04   
# MAINTAINER sss
# RUN apt-get update  
# RUN apt-get install -y openjdk-7-jdk  
# RUN apt-get install -y openssh-server  
# RUN mkdir /var/run/sshd  
# RUN echo 'root:rootroot' |chpasswd  
# RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config  
# RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config  
# EXPOSE 22 
# CMD ["/usr/sbin/sshd", "-D"]  


FROM alpine
MAINTAINER null
RUN echo "root:rootoor" |chpasswd && \
    apk add --no-cache openssh && \
    echo "PermitRootLogin yes" >> /etc/ssh/sshd_config  && \
    echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config
CMD ["/usr/sbin/sshd","-D"]
