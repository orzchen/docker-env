# 使用官方 PHP 和 Apache 镜像作为基础镜像
FROM php:7.2-apache

#RUN sed -i s/deb.debian.org/mirrors.cloud.tencent.com/g /etc/apt/sources.list
#RUN sed -i s/security.debian.org/mirrors.cloud.tencent.com/g /etc/apt/sources.list
#RUN apt update
#RUN export DEBIAN_FRONTEND=noninteractive
#RUN apt install -y tzdata zlib1g-dev libzip-dev libwebp-dev libjpeg-dev libpng-dev libfreetype6-dev

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

RUN install-php-extensions gd xdebug pdo pdo_mysql
