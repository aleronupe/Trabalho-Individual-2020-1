FROM ruby:2.5.7

RUN apt-get update -qq && apt-get install -y nodejs postgresql-client

WORKDIR /myapp

COPY Gemfile /myapp/Gemfile

COPY Gemfile.lock /myapp/Gemfile.lock

RUN gem install bundler

RUN bundle install

COPY . /myapp

# Add a script to be executed every time the container starts.
COPY entrypoint.sh /usr/bin/

ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.7.3/wait /wait

RUN chmod +x /wait

RUN chmod +x /usr/bin/entrypoint.sh

ENTRYPOINT ["entrypoint.sh"]

RUN curl -L https://codeclimate.com/downloads/test-reporter/test-reporter-latest-linux-amd64 > ./cc-test-reporter

RUN chmod +x ./cc-test-reporter

EXPOSE 3000

# Start the main process.

# CMD ["rails", "server", "-b", "0.0.0.0"]






