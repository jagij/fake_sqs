# This is based on https://github.com/airdock-io/docker-fake-sqs/blob/master/0.3.1/Dockerfile

FROM airdock/rvm:latest
MAINTAINER Jan Willem <jan.willem.ps@gmail.com>
USER root

COPY Gemfile Rakefile fake_sqs.gemspec /src/fake-sqs/
COPY lib/ /src/fake-sqs/lib/

WORKDIR /src/fake-sqs

RUN	rvm ruby-2.3 do gem build fake_sqs.gemspec && \
	rvm ruby-2.3 do gem install ./fake_sqs-0.4.3.gem

USER ruby

EXPOSE 4568

VOLUME ["/srv/ruby/fake-sqs"]

CMD ["tini", "-g", "--", "gosu", "ruby:ruby", "rvm", "ruby-2.3", "do", "fake_sqs", "--database", "/srv/ruby/fake-sqs/database.yml"]
