FROM php:5.6-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        zip \
        git \
        apt-transport-https \
        build-essential \
        curl \
        lsb-release \
        python-all \
        rlwrap

# install php extensions
RUN docker-php-ext-install iconv \
						mcrypt\
						pdo \
						pdo_mysql \
						mysqli \
						mysql \
						gd  \
						mbstring \
						zip
RUN docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr && \
docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd && \
docker-php-ext-configure mysql --with-mysql=mysqlnd && \
docker-php-ext-configure mysqli --with-mysqli=mysqlnd


CMD ["php-fpm"]

EXPOSE 9000