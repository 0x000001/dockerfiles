FROM rigormortiz/ubuntu-xrdp-mate:zesty
RUN useradd -ms /bin/bash nullun
RUN echo "nullun:rootoor" | chpasswd 
RUN usermod -aG sudo nullun
