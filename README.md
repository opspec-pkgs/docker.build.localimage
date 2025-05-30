[![build](https://github.com/opspec-pkgs/docker.build.localimage/actions/workflows/build.yml/badge.svg)](https://github.com/opspec-pkgs/docker.build.localimage/actions/workflows/build.yml)


# Problem statement

Build a docker image in your host machines docker image store. Once a successful run of this op completes, you should see your new container created on the host machine when you run `docker images`.

Example usage:

```yml
  op:
    ref: github.com/opspec-pkgs/docker.build.localimage#1.2.0
    inputs:
      imageName: my-image
      dockerfile: $(/Dockerfile)
      dockerfileStage: my-stage-name
      dockerSocket:
      dockerConfig:
        auths:
          "https://index.docker.io/v1/":
            auth: dXNlcm5hbWU6cGFzc3dvcmQK
```

```yml
  op:
    ref: github.com/opspec-pkgs/docker.build.localimage#1.2.0
    inputs:
      imageName: my-image
      dockerfile: $(/Dockerfile)
      dockerfileStage: my-stage-name
      dockerSocket:
      dockerConfig: $(HOME/.docker/config.json)
```


# Example usage

## Visualize

```shell
opctl ui github.com/opspec-pkgs/docker.build.localimage#1.2.0
```

## Run

```
opctl run github.com/opspec-pkgs/docker.build.localimage#1.2.0
```

## Compose

```yaml
op:
  ref: github.com/opspec-pkgs/docker.build.localimage#1.2.0
  inputs:
    dockerSocket:  # 👈 required; provide a value
    dockerfileStage:  # 👈 required; provide a value
    imageName:  # 👈 required; provide a value
  ## uncomment to override defaults
  #   dockerConfig: [object Object]
  #   dockerfile: .
```

# Support

join us on
[![Slack](https://img.shields.io/badge/slack-opctl-E01563.svg)](https://join.slack.com/t/opctl/shared_invite/zt-51zodvjn-Ul_UXfkhqYLWZPQTvNPp5w)
or
[open an issue](https://github.com/opspec-pkgs/docker.build.localimage/issues)

# Releases

releases are versioned according to
[![semver 2.0.0](https://img.shields.io/badge/semver-2.0.0-brightgreen.svg)](http://semver.org/spec/v2.0.0.html)
and [tagged](https://git-scm.com/book/en/v2/Git-Basics-Tagging); see
[CHANGELOG.md](CHANGELOG.md) for release notes

# Contributing

see
[project/CONTRIBUTING.md](https://github.com/opspec-pkgs/project/blob/main/CONTRIBUTING.md)
