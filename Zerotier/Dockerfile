FROM debian:latest
RUN apt-get update && apt-get upgrade -y; apt-get install gpg curl wget
WORKDIR /tec2home/zerotier/
RUN wget https://www.zerotier.com/misc/contact@zerotier.com.gpg
RUN curl -s 'https://pgp.mit.edu/pks/lookup?op=get&search=0x1657198823E52A61' | gpg --import && \
if z=$(curl -s 'https://install.zerotier.com/' | gpg); then echo "$z" | bash; fi
ENTRYPOINT 
