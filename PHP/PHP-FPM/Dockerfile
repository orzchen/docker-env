# 使用官方 PHP 7.4 FPM 镜像 - 版本切换
FROM php:7.3-fpm

# 设置国内镜像源
RUN sed -i s/deb.debian.org/mirrors.cloud.tencent.com/g /etc/apt/sources.list
RUN sed -i s/security.debian.org/mirrors.cloud.tencent.com/g /etc/apt/sources.list

# 更新 apt 包索引并安装 net-tools 和 iputils-ping
RUN apt-get update && apt-get install -y \
    net-tools \
    iputils-ping \
    && rm -rf /var/lib/apt/lists/*

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

# PHP 扩展安装
RUN install-php-extensions gd xdebug pdo pdo_mysql mysqli