# See https://github.com/docker-library/php/blob/master/7.1/fpm/Dockerfile
FROM elixir:1.10

MAINTAINER Borys Zielonka

RUN mix local.hex --force \
 && mix archive.install --force hex phx_new 1.4.15 \
 && apt-get update \
 && curl -sL https://deb.nodesource.com/setup_10.x | bash \
 && apt-get install -y apt-utils \
 && apt-get install -y nodejs \
 && apt-get install -y build-essential \
 && apt-get install -y inotify-tools \
 && mix local.rebar --force

ENV APP_HOME /var/www/phoenix_app
RUN mkdir -p $APP_HOME
WORKDIR $APP_HOME

CMD mix phx.server

EXPOSE 4000