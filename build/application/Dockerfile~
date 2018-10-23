FROM debian:jessie

MAINTAINER Paulo Dias <prbdias@gmail.com>
RUN echo "Asia/Shanghai" > /etc/timezone
RUN dpkg-reconfigure -f noninteractive tzdata

WORKDIR /var/www

RUN chown -R www-data /var/www/

CMD ["true"]
