# Dockerfile for sans-sift
FROM ubuntu:18.04
LABEL description="Sans-sift tools - Dockerimage"
MAINTAINER incidentresponsesandbox@gmail.com

# install sift
RUN mkdir -p /var/tmp/scripts
COPY install_script.sh /var/tmp/scripts
WORKDIR /var/tmp/scripts
RUN chmod +x install_script.sh
RUN ./install_script.sh

# sansforensics
USER sansforensics
WORKDIR /home/sansforensics
CMD ["/usr/bin/whoami"]