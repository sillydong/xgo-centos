# Go cross compiler (xgo): Base cross-compilation layer
# Copyright (c) 2014 Péter Szilágyi. All rights reserved.
#
# Released under the MIT license.

FROM sillydong/xgo-centos-base

MAINTAINER Péter Szilágyi <peterke@gmail.com>

RUN \
  export ROOT_DIST=https://storage.googleapis.com/golang/go1.10.2.linux-amd64.tar.gz     && \
  export ROOT_DIST_SHA=4b677d698c65370afa33757b6954ade60347aaca310ea92a63ed717d7cb0c2ff && \
  \
  $BOOTSTRAP_PURE

