FROM kalilinux/kali-rolling
LABEL description="Tools for performing social engineering"
MAINTAINER incidentresponsesandbox@gmail.com

USER root

# install social engineering tools
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && apt-get upgrade -y && \
    apt-get install -y set maltego metasploit-framework git \
                       python3-distutils python3-apt python3-pip dnsmasq \
                       libnl-3-dev libnl-genl-3-dev libssl-dev python3-setuptools cmake &&\
                       unset DEBIAN_FRONTEND

# install wifiphisher
RUN mkdir -p /opt/irsandbox/wifiphisher && \
             git clone https://github.com/wifiphisher/wifiphisher.git /opt/irsandbox/wifiphisher && \
             cd /opt/irsandbox/wifiphisher && \
             python3 setup.py install 

# change workdir
ENV TERM linux
WORKDIR /opt/irsandbox