FROM ruby:2.6

MAINTAINER Lynn Frank <fwebber@hashicorp.com>

RUN apt-get update  \
	&& apt-get install -y net-tools

ENV APP_HOME=/app
ENV HOME=/root
RUN mkdir $APP_HOME
WORKDIR /app

COPY Gemfile /app/
COPY Gemfile.lock /app/

RUN bundle install

COPY config.ru /app/

RUN mkdir $APP_HOME/lib

COPY service.rb /app/lib/

ENV PORT=8080
EXPOSE 8080
CMD ["rackup" "--port" "8080" "--env" "production"]
