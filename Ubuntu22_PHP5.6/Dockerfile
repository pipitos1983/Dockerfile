FROM ubuntu:22.04

RUN apt update && \
    apt upgrade -y && \
    apt install -y software-properties-common && \
    add-apt-repository ppa:ondrej/php && \
    apt update && \
    DEBIAN_FRONTEND=noninteractive apt install -y php5.6 \
        php5.6-gd \
        php5.6-mysql \
        php5.6-imap \
        php5.6-curl \
        php5.6-intl \
        php5.6-pspell \
        php5.6-recode \
        php5.6-sqlite3 \
        php5.6-tidy \
        php5.6-xmlrpc \
        php5.6-xsl \
        php5.6-zip \
        php5.6-mbstring \
        php5.6-soap \
        php5.6-opcache \
        php5.6-common \
        php5.6-json \
        php5.6-readline \
        php5.6-xml \
        php5.6-pgsql \
        apache2 \
        libapache2-mod-php5.6  && \
    a2enmod rewrite && \
    a2enmod headers && \
    a2enmod rewrite && \
    a2enmod php5.6 && \
    apt clean && rm -r /var/lib/apt/lists/*

RUN echo '<?php phpinfo();  ?>' > /var/www/html/info.php

WORKDIR /var/www/html
EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]
