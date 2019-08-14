FROM ruby:2.6.0

RUN apt-get update
RUN apt-get install -y git curl gnupg

RUN git clone https://github.com/docker-hy/rails-example-project.git

WORKDIR /rails-example-project

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs

RUN node -v && npm -v

RUN npm install



RUN gem install bundler

RUN bundle install

RUN rails db:migrate

EXPOSE 3000

CMD ["rails", "s"]
