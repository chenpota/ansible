FROM ubuntu:16.04
MAINTAINER cpt94@iii.org.tw

RUN apt-get update \
 && apt-get install -y \
        build-essential \
        openssh-client \
        python-setuptools \
        python-dev \
        sshpass \
        wget \
 && rm -rf \
        /var/cache/apt/* \
        /var/lib/apt/* \
 && wget http://curl.haxx.se/ca/cacert.pem \
 && mkdir /etc/pki/tls -p \
 && mv cacert.pem /etc/pki/tls/certs \
 && easy_install pip \
 && pip install ansible \
