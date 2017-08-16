FROM ubuntu:16.04
MAINTAINER cpt94@iii.org.tw

RUN apt-get update \
 && apt-get install -y \
        build-essential \
        openssh-server \
        python-setuptools \
        python-dev \
        wget \
 && rm -rf \
        /var/cache/apt/* \
        /var/lib/apt/* \
 && wget http://curl.haxx.se/ca/cacert.pem \
 && mkdir /etc/pki/tls -p \
 && mv cacert.pem /etc/pki/tls/certs \
 && easy_install pip \
 && mkdir /var/run/sshd \
 && echo 'root:root' |chpasswd \
 && sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config \
 && sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD /usr/sbin/sshd -D
