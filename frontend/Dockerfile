FROM ubuntu
RUN export DEBIAN_FRONTEND=noninteractive
RUN apt-get install -y tzdata
RUN ln -fs /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
RUN dpkg-reconfigure --frontend noninteractive tzdata
RUN apt-get update && apt-get install -y apache2 && apt-get -y clean
ADD frontend.tar.gz /var/www/html/
ADD mod_status /tmp/
RUN cat /tmp/mod_status > /etc/apache2/mods-enabled/status.conf
EXPOSE 80
CMD apachectl -D FOREGROUND
