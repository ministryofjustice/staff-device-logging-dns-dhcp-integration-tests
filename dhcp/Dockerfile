FROM debian:buster-slim

USER root

RUN apt-get update && apt-get install -y curl \
    debian-keyring \
    debian-archive-keyring \
    apt-transport-https
RUN curl -1sLf 'https://dl.cloudsmith.io/public/isc/kea-1-6/cfg/gpg/gpg.0607E2621F1564A6.key' | apt-key add -
RUN curl -1sLf 'https://dl.cloudsmith.io/public/isc/kea-1-6/cfg/setup/config.deb.txt?distro=debian&codename=buster' > /etc/apt/sources.list.d/isc-kea-1-6.list
RUN apt-get update && apt-get install -y isc-kea-*

WORKDIR /home
RUN chown root:root /home
RUN  mkdir /var/run/kea

EXPOSE 67/udp
EXPOSE 68/udp

CMD ["perfdhcp", "10.180.81.4", "-n", "100", "-r", "5", "-R", "5"]
