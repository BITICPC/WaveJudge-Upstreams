ARG basever=stretch
FROM debian:${basever}-slim AS build
WORKDIR /srctree

# Install necessary utilities.
RUN apt-get --assume-yes update &&  apt-get --assume-yes install git build-essential

# Clone openssl repository
RUN git clone https://github.com/openssl/openssl.git
WORKDIR /srctree/openssl

# Build openssl from source
ARG branch=OpenSSL_1_1_1-stable
RUN git checkout ${branch}
RUN ./config --prefix=/openssl/install --openssldir=/openssl/config && make && make install

# Compose the final image, discarding the source files.
FROM debian:${basever}-slim AS final
WORKDIR /openssl
COPY --from=build /openssl/* ./
