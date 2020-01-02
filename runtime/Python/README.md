# Python docker image

This docker image contains a prebuilt copy of python 3.x. The available tags now are:

* `3.5.9-stretch`
* `3.6.10-stretch`
* `3.7.6-stretch`
* `3.8.1-stretch`

All images are built based on an official debian image.

## Build Args

Two build args are available to build the docker image:

* `basever`: The version of debian that the docker image is based on. The default value is `stretch`.
* `pyver`: Version of python to build. The default value is `3.8.1`.

## Image Layout

The final image contains the directory `/python`. This directory is the install directory specified by the `--prefix` option when configuring python source tree.
