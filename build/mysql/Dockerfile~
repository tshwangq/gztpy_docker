FROM mysql:5.7

MAINTAINER Paulo Dias <prbdias@gmail.com>
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata
CMD ["mysqld"]

EXPOSE 3306
