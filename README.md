<h1>Danger Docker Image</h1>

[![CircleCI Build Status](https://circleci.com/gh/BytesGuy/danger-docker.svg?style=shield)](https://circleci.com/gh/BytesGuy/danger-docker) [![Software License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/BytesGuy/danger-dockermaster/LICENSE) [![Docker Pulls](https://img.shields.io/docker/pulls/bytesguy/danger)](https://hub.docker.com/r/bytesguy/danger)

`bytesguy/danger` is a docker image designed to make using danger easy, particulary in CircleCI jobs. Danger is a tool to automate your team's conventions surrounding code review. More information about danger can be found at the [danger repo](https://github.com/danger/danger).

You can find the image on [DockerHub](https://hub.docker.com/r/bytesguy/danger)

## Getting Started

An example of how to use this image with CircleCI can be found below:

```
version: 2.1

jobs:
  danger:
    docker:
        - image: bytesguy/danger:latest
    steps:
        - checkout
        - run: danger
```

The same command applies to running this image in other environments, simply call `danger` in your project directory.

Why use this docker image instead of calling danger in your macOS job?

- danger can be run in parallel with the build, saving overall build time
- Running danger in docker also saves build credits as the Docker executor is cheaper to use

More information about a multi executor setup can be found in the [CircleCI iOS Documentation](https://circleci.com/docs/2.0/testing-ios/#using-multiple-executor-types-macos--docker).

## Image Information

Each time danger is updated, there will be a new, version tagged, release of the danger docker image. The latest version of Ruby will always be used at the time of building.

The images are built on the official CircleCI base image to ensure compatbility with CircleCI jobs.

The Dockerfile for each version can be found in the `versions` directory.