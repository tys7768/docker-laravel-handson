# FROM命令 イメージビルドのための、ベースイメージを設定する。 イメージ名:タグ名
FROM php:7.4-fpm-buster
# SHELL命令
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

# ENV命令 コンテナ内のサーバー環境変数を設定する
ENV COMPOSER_ALLOW_SUPERUSER=1 \
  COMPOSER_HOME=/composer

COPY --from=composer:1.10 /usr/bin/composer /usr/bin/composer

# 色々やる。最後にphp拡張ライブラリをインストールしたり
RUN apt-get update && \
  apt-get -y install git unzip libzip-dev libicu-dev libonig-dev && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  docker-php-ext-install intl pdo_mysql zip bcmath

COPY ./php.ini /usr/local/etc/php/php.ini

WORKDIR /work
