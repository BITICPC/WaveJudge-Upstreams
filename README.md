# WaveJudge-Upstreams

This repository maintains the upstream packages required by `WaveJudge`. The upstream packages are all available through docker images. Each upstream package are maintained separately inside different subdirectories of the `build` directory or the `runtime` directory. For details about the usage of the docker images of the upstream packages, please refer to the `README.md` files under the same directory as their dockerfile.

## Directories

### `build`

This repository contains upstream packages required in the build phase of `WaveJudge`. They are:

* OpenSSL;
* libseccomp.

### `runtime`

This repository contains upstream packages required to run `WaveJudge`. They are:

* Python 3.5
* Python 3.6
* Python 3.7
* Java 13
