FROM php:5.6-fpm

MAINTAINER Qun Wang <tshwangq@gmail.com>

#RUN echo "Asia/Shanghai" > /etc/timezone
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata

COPY ./php.ini /usr/local/etc/php/

RUN apt-get update && apt-get install -y \
    libpq-dev libfreetype6-dev libmcrypt-dev libjpeg-dev libpng-dev \
    curl

RUN    docker-php-ext-install iconv mcrypt
RUN  docker-php-ext-configure gd \
    --enable-gd-native-ttf \
    --with-freetype-dir=/usr/include/freetype2 \
    --with-png-dir=/usr/include \
    --with-jpeg-dir=/usr/include
# Install extensions using the helper script provided by the base image
RUN docker-php-ext-install \
    mysql mysqli pdo pdo_mysql \
    pdo_pgsql \
    mbstring \
    gd

RUN  docker-php-ext-enable gd

RUN usermod -u 1000 www-data

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
