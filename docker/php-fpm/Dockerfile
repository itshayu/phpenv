FROM php:7.4.2-fpm-alpine3.11
WORKDIR "/app"

# https://github.com/mlocati/docker-php-extension-installer
# 更新apt-get源
RUN set -eux && \
    sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories && \
    apk update && \
    apk add --no-cache \
        tzdata \
        curl-dev \
        libcurl \
        curl \
        zip \
        libzip-dev \
        graphviz \
        ttf-dejavu \
        fontconfig \
        font-bitstream-type1 \
        ghostscript-fonts \
        ttf-cantarell \
        font-noto \
        oniguruma-dev && \
    cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo "Asia/Shanghai" > /etc/timezone && \
    apk del tzdata && \
    docker-php-ext-install zip pdo pdo_mysql mysqli fileinfo mbstring curl exif && \
    curl -sSLf \
        -o /usr/local/bin/install-php-extensions \
        https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
    chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions \
        imagick \
        xdebug \
        swoole \
        redis \
        rdkafka \
        yaml \
        pcntl \
        mongodb \
        bcmath \
        shmop \
        sysvsem \
        sockets \
        memcached \
        xhprof
