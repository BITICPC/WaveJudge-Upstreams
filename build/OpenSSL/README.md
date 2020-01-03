# `OpenSSL` docker image

This docker image provides a built version of the `OpenSSL` library.

## Build Arguments

The following build arguments are available:

* `basever`: Specify the version of the base image. This docker image will always use Debian official image as its base image, you can use `basever` to indicate the version of Debian distributions to be used. The default value of `basever` is `stretch`.
* `branch`: The branch to checkout in the `openssl` repository before building it. The default value of `branch` is `OpenSSL_1_1_1-stable`.

## Image Layout

After successfully built, this docker image will have a directory `/openssl` containing a installation of `openssl`. The `/openssl/install` directory is the install prefix of `openssl` during build, and the `/openssl/static` directory is the directory containing the OpenSSL configuration and the root certificates.
