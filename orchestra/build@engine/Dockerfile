FROM ubuntu

WORKDIR /var/tmp

RUN apt-get update \
	&& DEBIAN_FRONTEND=noninteractive \
	apt-get install -y dnsmasq dnsutils


EXPOSE 53/tcp
EXPOSE 53/udp

CMD ["dnsmasq","-k"]
