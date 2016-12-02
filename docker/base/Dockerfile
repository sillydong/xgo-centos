# Go cross compiler (xgo): Base cross-compilation layer
# Copyright (c) 2014 Péter Szilágyi. All rights reserved.
#
# Released under the MIT license.

FROM centos:centos6.6

MAINTAINER Péter Szilágyi <peterke@gmail.com>

# Mark the image as xgo enabled to support xgo-in-xgo
ENV XGO_IN_XGO 1


# Configure the Go environment, since it's not going to change
ENV PATH   /usr/local/go/bin:$PATH
ENV GOPATH /go


# Inject the remote file fetcher and checksum verifier
ADD fetch.sh /fetch.sh
ENV FETCH /fetch.sh
RUN chmod +x $FETCH


# Make sure yum is up to date and dependent packages are installed
RUN \
  yum -y install glibc.i686 glibc-devel.i686 glibc.x86_64 glibc-devel.x86_64 glibc-headers.x86_64 glibc-static.i686 glibc-static.x86_64 glibc-utils.x86_64 libgcc.i686 libgcc.x86_64 libstdc++.i686 libstdc++.x86_64 ibstdc++-devel.i686 libstdc++-devel.x86_64 patch make gcc gcc-c++ automake cmake autoconf libtool libtool-libs zlib zlib-devel glib2 glib2-devel bzip2 bzip2-devel libevent libevent-devel ca-certificates make cpio wget zip unzip p7zip git mercurial bzr texinfo help2man tar

# Fix any stock package issues
RUN ln -s /usr/include/asm-generic /usr/include/asm

# Inject the new Go root distribution downloader and bootstrapper
ADD bootstrap_pure.sh /bootstrap_pure.sh
ENV BOOTSTRAP_PURE /bootstrap_pure.sh
RUN chmod +x $BOOTSTRAP_PURE

# Inject the C dependency cross compiler
ADD build_deps.sh /build_deps.sh
ENV BUILD_DEPS /build_deps.sh
RUN chmod +x $BUILD_DEPS

# Inject the container entry point, the build script
ADD build.sh /build.sh
ENV BUILD /build.sh
RUN chmod +x $BUILD

ENTRYPOINT ["/build.sh"]
