FROM cimg/ruby:2.7.1

LABEL maintainer="BytesGuy <bytesguy@users.noreply.github.com>"

ENV DANGER_VERSION 8.0.0

USER root
WORKDIR /home/circleci
RUN apt-get update && apt-get install -y --no-install-recommends p7zip && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN gem install danger -v ${DANGER_VERSION}

USER circleci
WORKDIR /home/circleci/project