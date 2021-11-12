FROM kalilinux/kali-rolling
LABEL description="Tools for Pentesting"
MAINTAINER incidentresponsesandbox@gmail.com

USER root
ENV PATH="/root/go/bin:${PATH}"

# install subdomain enumeration tools
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && apt-get upgrade -y && \
    apt-get install -y sslscan sqlmap dirb apktool john sublist3r amass \
                       golang build-essential manpages-dev lynis wpscan \
                       python3-pip git dnsrecon altdns nikto \
                       aircrack-ng recon-ng hydra skipfish beef hashcat whatweb \
                       gobuster wfuzz joomscan netcat-openbsd telnet \
                       smbclient enum4linux unicornscan masscan &&\
                       unset DEBIAN_FRONTEND

# install golang based tools
RUN go get -u github.com/tomnomnom/assetfinder && \
    go get -u github.com/tomnomnom/httprobe && \
    go get -u github.com/sensepost/gowitness && \
    go get github.com/haccer/subjack

# install knock
RUN mkdir -p /opt/irsandbox/knock &&\
             git clone https://github.com/guelfoweb/knock.git /opt/irsandbox/knock && \
             pip3 install -r /opt/irsandbox/knock/requirements.txt 

# install subbrute
RUN mkdir -p /opt/irsandbox/subbrute &&\
             git clone https://github.com/TheRook/subbrute.git /opt/irsandbox/subbrute

# change workdir
ENV TERM linux
WORKDIR /opt/irsandbox