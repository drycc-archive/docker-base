# Drycc Base

[![Build Status](https://travis-ci.org/drycc/docker-base.svg?branch=master)](https://travis-ci.org/drycc/docker-base) [![Docker Repository on Quay](https://quay.io/repository/drycc/base/status "Docker Repository on Quay")](https://quay.io/repository/drycc/base)

A slimmed-down Ubuntu-based container image used as the basis of [Drycc Workflow][] and other components.

## Usage

Start your Dockerfile with this line:

```
FROM quay.io/drycc/base:v0.3.7
```

There isn't a `:latest` tag, because tagged container images should be immutable.

The latest drycc/base image is available at:

* [Quay.io][]
  ```
  docker pull quay.io/drycc/base:v0.3.7
  ```

* [Docker Hub][]
  ```
  docker pull drycc/base:v0.3.7
  ```

## Updating Downstream Images

Lots of Workflow components rely on drycc/base. In order to update the downstream repos with the
new image, run `OLD_VERSION="v0.3.7" NEW_VERSION="v0.3.8" ./_scripts/make-prs.sh`. This will
clone all the downstream repos in /tmp, change the image, commit the change and push it to a new
branch. The script will then open a browser window to make a PR against master for that repo.

[Drycc Workflow]: https://drycc.com/
[Quay.io]: https://quay.io/repository/drycc/base
[Docker Hub]: https://hub.docker.com/r/drycc/base/
