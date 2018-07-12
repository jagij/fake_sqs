# Fake SQS

Fake SQS is a lightweight server that mocks the Amazon SQS API.

It is extremely useful for testing SQS applications in a sandbox environment without actually
making calls to Amazon, which not only requires a network connection, but also costs
money.

Many features are supported and if you miss something, open a pull.

This is a fork from [lukfugl/fake_sqs](https://github.com/lukfugl/fake_sqs), which includes support for long-polling.

## Installation

```
gem install fake_sqs
```

## Running

```
fake_sqs --database /path/to/database.yml
```

## Development

```
bundle install
rake
```

## Deploy docker to dockerhub
```
docker build --rm -t jagij/fake-sqs -f docker/Dockerfile .
docker login
docker tag jagij/fake-sqs jagij/fake-sqs:latest
docker push jagij/fake-sqs:latest
```
