[![Build Status](https://travis-ci.org/opspec-pkgs/docker.build.localimage.svg?branch=master)](https://travis-ci.org/opspec-pkgs/docker.build.localimage)

# Problem statement

Builds image that stores on host machines docker image store.
* `dockerSocket` must be the correct socket path to the host machine's `dockerd` runtime socket IE `/var/run/docker.sock` (default path). For linux, you can try `netstat -lx | grep docker | grep -Po '/.*docker.sock'` to verify the proper socket file.
* `imageName` is the name of the image you want to give the resultant image for `docker build`
* `dockerfile` is the path to (including) the Dockerfile from which you will build the image.

Once a successful run of this op completes, you should see your new container created on the host machine using `docker images`.


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

```yaml
op:
  ref: github.com/opspec-pkgs/docker.build.localimage#1.0.0
  inputs:
    dockerSocket:
    imageName:
    # params w/ default
    dockerfile:
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
