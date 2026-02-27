FROM ubuntu

WORKDIR /var/tmp

RUN apt-get update \
	&& DEBIAN_FRONTEND=noninteractive \
	apt-get install -y dnsmasq dnsutils

RUN cp -f /etc/dnsmasq.conf /etc/dnsmasq.original.txt
RUN grep -v -E '(^[#;]|^$)' /etc/dnsmasq.original.txt | tee /etc/dnsmasq.conf

RUN echo 'conf-dir=/etc/dnsmasq.d/,*.conf' >> /etc/dnsmasq.conf

EXPOSE 53/tcp
EXPOSE 53/udp

CMD ["dnsmasq","-k"]
