FROM ubuntu:14.04

RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get -y install php5-fpm
RUN apt-get -y install php5-mysql
RUN apt-get -y install git

ADD www.conf /etc/php5/fpm/pool.d/www.conf
ADD php.ini /etc/php5/fpm/php.ini

RUN git clone https://github.com/X2k16/student-cupon.git /app
ADD config.php /app/config.php

VOLUME /app
EXPOSE 9000
CMD ["/usr/sbin/php5-fpm", "--nodaemonize", "--fpm-config", "/etc/php5/fpm/php-fpm.conf"]
