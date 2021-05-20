[![Build Status](https://travis-ci.org/opspec-pkgs/docker.build.localimage.svg?branch=master)](https://travis-ci.org/opspec-pkgs/docker.build.localimage)

# Problem statement

Build a docker image in your host machines docker image store. Once a successful run of this op completes, you should see your new container created on the host machine when you run `docker images`.

## Inputs

### `dockerfile`

The path the Dockerfile from which you will build the image or a directory containing one named `Dockerfile`.

### `dockerSocket`

The socket path to the host machine's `dockerd` runtime socket.

For linux, you can try `netstat -lx | grep docker | grep -Po '/.*docker.sock'` to verify the proper socket file. For macOS, the default is `/var/run/docker.sock`.

### `dockerConfig`

The JSON of a docker configuration file. Use this to provide authentication to the docker registry.

Note that when using a credential helper (the default with macOS docker desktop) your default docker config at ~/.docker/config.json will not directly contain credentials. If you need to provide auth in this case, you'll need to generate a configuration file with base64 encoded credentials. See https://github.com/docker/for-mac/issues/4100 for more discussion on the format of this file.

### `imageName`

The name (tag) of the built image. e.g. "container_name:latest".

# Format

the op uses [![opspec 0.1.5](https://img.shields.io/badge/opspec-0.1.5-brightgreen.svg?colorA=6b6b6b&colorB=fc16be)](https://opspec.io/0.1.5) definition format

# Example usage

## Install

```shell
opctl op install github.com/opspec-pkgs/docker.build.localimage#1.0.0
```

## Run

```
opctl run github.com/opspec-pkgs/docker.build.localimage#1.0.0
```

## Compose

```yml
  op:
    ref: github.com/opspec-pkgs/docker.build.localimage#1.0.0
    inputs:
      imageName: my-image
      dockerfile: $(/Dockerfile)
      dockerSocket:
      dockerConfig:
        auths:
          "https://index.docker.io/v1/":
            auth: dXNlcm5hbWU6cGFzc3dvcmQK
```

```yml
  op:
    ref: github.com/opspec-pkgs/docker.build.localimage#1.0.0
    inputs:
      imageName: my-image
      dockerfile: $(/Dockerfile)
      dockerSocket:
      dockerConfig: $(HOME/.docker/config.json)
```

# Support

join us on
[![Slack](https://opctl-slackin.herokuapp.com/badge.svg)](https://opctl-slackin.herokuapp.com/)
or
[open an issue](https://github.com/opspec-pkgs/docker.build.localimage/issues)

# Releases

releases are versioned according to
[![semver 2.0.0](https://img.shields.io/badge/semver-2.0.0-brightgreen.svg)](http://semver.org/spec/v2.0.0.html)
and [tagged](https://git-scm.com/book/en/v2/Git-Basics-Tagging); see
[CHANGELOG.md](CHANGELOG.md) for release notes

# Contributing

see
[project/CONTRIBUTING.md](https://github.com/opspec-pkgs/project/blob/master/CONTRIBUTING.md)
