# Go cross compiler (xgo): Base cross-compilation layer
# Copyright (c) 2014 Péter Szilágyi. All rights reserved.
#
# Released under the MIT license.

FROM sillydong/xgo-centos-base

MAINTAINER Péter Szilágyi <peterke@gmail.com>

RUN \
  export ROOT_DIST=http://golangtc.com/static/go/1.7.3/go1.7.3.linux-amd64.tar.gz     && \
  export ROOT_DIST_SHA=508028aac0654e993564b6e2014bf2d4a9751e3b286661b0b0040046cf18028e && \
  \
  $BOOTSTRAP_PURE
