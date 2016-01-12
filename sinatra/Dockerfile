FROM alpine:3.3

RUN apk add --no-cache ruby ruby-io-console ruby-bundler

WORKDIR /app
ADD Gemfile /app/Gemfile
#ADD Gemfile.lock /app/Gemfile.lock
RUN ["/usr/bin/bundle", "install"]
ADD . /app

EXPOSE 8080
CMD []
ENV APPSERVER webrick
ENV RACK_ENV production
ENTRYPOINT /usr/bin/bundle exec rackup \
    -p 8080 /app/config.ru -s $APPSERVER -E $RACK_ENV