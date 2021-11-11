FROM kalilinux/kali-rolling
LABEL description="Tools for performing social engineering"
MAINTAINER incidentresponsesandbox@gmail.com

USER root

# install social engineering tools
RUN export DEBIAN_FRONTEND=noninteractive && \
    apt-get update && apt-get upgrade -y && \
    apt-get install -y set maltego metasploit-framework &&\
                       unset DEBIAN_FRONTEND

# change workdir
ENV TERM linux
WORKDIR /root