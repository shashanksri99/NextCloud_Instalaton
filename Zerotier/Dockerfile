FROM debian:latest
#Setting up the environment variable inside the container to setup the proxy.
ENV http_proxy=shashank_sr:Nov\@2018@10.112.50.97:8080
#The following add will only work in office computer as proxy is required for running commands in side the container.
ADD /etc/apt/apt.conf.d/95proxies /etc/apt/apt.conf.d/
#updating and upgrading the the system and installing all the required softwares
RUN apt-get update && apt-get upgrade -y; apt-get install -y gpg curl wget
#creating a directory for placing the key file for zerotier software
RUN mkdir ~/.gnupg
ADD ~/Documents/Raspberry_pi_Docker/NextCloud_Instalaton/Zerotier/contact@zerotier.com.gpg ~/.gnupg/
RUN curl -s 'https://pgp.mit.edu/pks/lookup?op=get&search=0x1657198823E52A61' | gpg --import && \
if z=$(curl -s 'https://install.zerotier.com/' | gpg); then echo "$z" | bash; fi
