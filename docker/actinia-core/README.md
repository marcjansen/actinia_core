# actinia docker image

A related docker image created and available for download from here:

https://hub.docker.com/r/mundialis/actinia-core

## Background info

This docker image is based on https://hub.docker.com/r/mundialis/grass-py3-pdal which provides GRASS GIS 7.8 (release branch, grass78) with python3 and PDAL support.

The Dockerfile contained in this folder is used to build to dockerhub.
If you want to build manually...
## mind the build context!

Clone this repository and change directory:

```bash
$ git clone https://github.com/mundialis/actinia_core.git
$ cd actinia_core
```

__Build the docker with__:

```bash
$ docker build \
         --file docker/actinia-core/Dockerfile \
         --tag actinia-core:latest .
```

View the images available using `sudo docker images` and open a bash terminal with:

```bash
$ docker run -it --entrypoint=/bin/bash actinia-core:latest
root@c5e3b72ad8ba:/grassdb#
```

__To build a stable version__:

change to the tag you want to build (only supported from v0.2.3):
```bash
$ git checkout v0.2.3
```

and build and enter with:

```bash
$ docker build \
        --file docker/actinia-core/Dockerfile \
        --tag actinia-core:stable .

$ docker run -it --entrypoint=/bin/bash actinia-core:latest
root@c5e3b72ad8ba:/grassdb#
```