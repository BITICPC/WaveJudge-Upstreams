ARG basever=stretch
FROM debian:${basever}-slim AS build
WORKDIR /srctree

# Install necessary utilities.
RUN apt-get --assume-yes update &&  apt-get --assume-yes install git build-essential

# Clone libseccomp repository
RUN git clone https://github.com/seccomp/libseccomp
WORKDIR /srctree/libseccomp

# Build libseccomp from source
ARG branch=release-2.4
RUN git checkout ${branch}
RUN ./autogen.sh && ./configure --prefix=/libseccomp && make && make install

# Compose the final image, discarding the source files.
FROM debian:${basever}-slim AS final
WORKDIR /libseccomp
COPY --from=build /libseccomp/* ./
