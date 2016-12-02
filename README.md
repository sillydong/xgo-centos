# xgo - Go CGO cross compiler

**Use CentOS 6.6 instead of Ubuntu 16.04 to support old glibc**

**Support only linux/amd64 and linux/386** 

**Support only golang 1.7.3+**

## Install

`docker pull sillydong/xgo-centos-latest`

**image is pushing**

`go get -u github.com/sillydong/xgo-centos`

## Build

build current directory

`xgo-centos .`

build current directory to linux/amd64

`xgo-centos --targets=linux/amd64 .`

**Further information and "how to" visit [karalabe/xgo](https://github.com/karalabe/xgo), just change `xgo` to `xgo-centos`**
