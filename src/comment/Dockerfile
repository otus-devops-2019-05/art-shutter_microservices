FROM alpine:latest
RUN apk update && apk upgrade && apk add build-base && apk add ruby-full ruby-dev && rm -rf /var/cache/apk/* && gem install bundler:1.17.2

ENV APP_HOME /app
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

ADD Gemfile* $APP_HOME/
RUN bundle install
ADD . $APP_HOME

ENV COMMENT_DATABASE_HOST comment_db
ENV COMMENT_DATABASE comments

CMD ["puma"]
