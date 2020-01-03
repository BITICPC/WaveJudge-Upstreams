ARG basever=stretch
FROM debian:${basever}-slim AS build
WORKDIR /srctree

# Install wget and build-essential utilities.
RUN apt-get --assume-yes update && apt-get --assume-yes install wget build-essential zlib1g-dev

# Get the source code tarball of the specified python version.
ARG pyver=3.8.1
RUN wget https://www.python.org/ftp/python/${pyver}/Python-${pyver}.tar.xz && \
    tar -xf Python-${pyver}.tar.xz
WORKDIR /srctree/Python-${pyver}

RUN ./configure --prefix=/python && make && make install

# Compose the final docker image, discard the source code.
FROM debian:${basever}-slim AS final
WORKDIR /python
COPY --from=build /python ./
