FROM phpdockerio/php71-fpm:latest

MAINTAINER Rain <ychy00001@163.com>

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
