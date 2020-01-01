# `libseccomp` docker image

This docker image provides a built version of the `libseccomp` library.

## Build Arguments

The following build arguments are available:

* `basever`: Specify the version of the base image. This docker image will always use Debian official image as its base image, you can use `basever` to indicate the version of Debian distributions to be used. The default value of `basever` is `stretch`.
* `branch`: The branch to checkout in the `libseccomp` repository before building it. The default value of `branch` is `release-2.4`.

## Image Layout

After successfully built, this docker image will have a directory `/libseccomp` containing a installation of `libseccomp`. The `/libseccomp` directory is the install prefix of `libseccomp` during build.
