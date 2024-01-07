FROM ruby:3.2-alpine

# Install SQLite
RUN apk --no-cache add sqlite
# Install Make
RUN apk add --no-cache make
# Install SQLite
RUN apk update && apk add --virtual build-dependencies build-base
# Install Git
RUN apk add git
# throw errors if Gemfile has been modified since Gemfile.lock
RUN bundle config --global frozen 1

WORKDIR /usr/src/app

COPY Gemfile Gemfile.lock ./

RUN gem i bundler
RUN bundle install

COPY . .

# CMD ["ruby", "bin", "server", "-b", "0.0.0.0"]
