FROM php:7.0-fpm

RUN apt-get update

# Install opcache
RUN docker-php-ext-install opcache

# Install APCu
RUN pecl install apcu
RUN echo "extension=apcu.so" > /usr/local/etc/php/conf.d/apcu.ini

# Install GD
RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng12-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install gd

# Install JSON
RUN docker-php-ext-install json

# Install mbstring
RUN docker-php-ext-install mbstring

# Install mcrypt
RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install mcrypt

# Install PDO
RUN docker-php-ext-install pdo_mysql

# Install memcached
COPY memcached-2.2.0.zip memcached-2.2.0.zip
RUN apt-get install -y unzip libmemcached-dev zlib1g-dev libncurses5-dev
RUN mkdir /usr/src/php/ext/memcached-2.2.0
RUN unzip memcached-2.2.0.zip -d /usr/src/php/ext/memcached-2.2.0
RUN rm memcached-2.2.0.zip
RUN docker-php-ext-install memcached-2.2.0

# Install Mongo
COPY mongo-1.1.5.zip mongo-1.1.5.zip
RUN apt-get install -y libssl-dev
RUN mkdir /usr/src/php/ext/mongo-1.1.5
RUN unzip mongo-1.1.5.zip -d /usr/src/php/ext/mongo-1.1.5
RUN rm mongo-1.1.5.zip
RUN docker-php-ext-install mongo-1.1.5

# Install intl
RUN apt-get install -y libicu-dev
RUN docker-php-ext-install intl

ADD php.ini /usr/local/etc/php/php.ini

EXPOSE 9000

CMD ["php-fpm"]
