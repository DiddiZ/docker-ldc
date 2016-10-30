[![Docker pulls](https://img.shields.io/docker/pulls/dlanguage/ldc.svg)](https://hub.docker.com/r/dlanguage/ldc/)
[![Docker Build](https://img.shields.io/docker/automated/dlanguage/ldc.svg)](https://hub.docker.com/r/dlanguage/ldc/)
[![Latest Tag](https://img.shields.io/github/tag/lindt/docker-ldc.svg)](https://hub.docker.com/r/dlanguage/ldc/)

# docker-ldc

Docker Image for LDC

Docker Image for LLVM-based [D](http://dlang.org) Compiler.

## Motivation

Installation of a compiler sometimes is cumbersome. This Docker image should take this pain and allow you to easily switch between Versions of the same compiler and even different compilers.

In case a native installation is required, `curl -fsS https://dlang.org/install.sh | bash -s ldc` could be used.

## Other Compilers

Allows to use all major D Compilers without installation.

| Compiler | Latest Tag |
| -------- | ---------- |
| DMD      | [![Latest Tag](https://img.shields.io/github/tag/lindt/docker-dmd.svg)](https://hub.docker.com/r/dlanguage/dmd/) |
| LDC      | [![Latest Tag](https://img.shields.io/github/tag/lindt/docker-ldc.svg)](https://hub.docker.com/r/dlanguage/ldc/) |
| GDC      | [![Latest Tag](https://img.shields.io/github/tag/lindt/docker-gdc.svg)](https://hub.docker.com/r/dlanguage/gdc/) |

## Usage

Place a `test.d` in your current directory.
Then execute
```
docker run --rm -ti \
  -e USER -e HOME -e LOCAL_USER_ID=`id -u $USER` -e LOCAL_GROUP_ID=`id -g $USER`
  -w $(pwd) \
  -v /home/$USER:/home/$USER \
  dlanguage/ldc ldc2 test.d
```
