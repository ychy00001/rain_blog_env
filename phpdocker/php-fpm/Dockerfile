FROM phpdockerio/php71-fpm:latest

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install  php-memcached php7.1-mysql \
php7.1-pgsql php-redis php7.1-bz2 php7.1-imap php7.1-bcmath php7.1-mbstring  \
php7.1-gd php7.1-odbc php-ssh2 php7.1-mcrypt php7.1-curl php-xdebug php7.1-zip \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# 安装 git curl vim zip
RUN apt-get update && apt-get install -y git curl vim libfreetype6-dev \
  && rm -rf /var/lib/apt/list* 

# 安装 composer
RUN curl -o composer.phar https://getcomposer.org/download/1.7.1/composer.phar \
  && chmod +x composer.phar

# 配置 composer ，将镜像源改为中国国内
RUN mv composer.phar /usr/local/bin/composer \
   && echo 'export PATH="$PATH:$HOME/.composer/vendor/bin"' >> ~/.profile \
   && . ~/.profile \
   && composer config -g repo.packagist composer https://packagist.phpcomposer.com
   
# 设置 Git 的身份
RUN git config --global user.name "yangchunyu" \
  && git config --global user.email "yangchunyu00001@163.com"

WORKDIR "/application"
