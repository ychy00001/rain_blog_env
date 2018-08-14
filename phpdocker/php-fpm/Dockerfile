FROM phpdockerio/php71-fpm:latest

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php-memcached php7.1-mysql \
php7.1-pgsql php-redis php7.1-bz2 php7.1-imap php7.1-bcmath php7.1-mbstring  \
php7.1-gd php7.1-odbc php-ssh2 php7.1-mcrypt php7.1-curl php-xdebug php7.1-zip \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*


WORKDIR "/application"
