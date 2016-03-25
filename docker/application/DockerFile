FROM ubuntu:14.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    git \
    curl \
    php5-cli \
    php5-json \
    php5-intl \
	php5-sqlite

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

VOLUME /var/www

ADD entrypoint.sh /

WORKDIR /var/www

# ENTRYPOINT ["/entrypoint.sh"]

CMD ["/bin/bash"]