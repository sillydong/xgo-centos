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

## Update Image

add go version

visit golang versions

`https://storage.googleapis.com/golang/`

find your version file and sha256, update Dockerfile

run build {VERSION}

`docker build -t sillydong/xgo-centos-{VERSION} .`

push to docker hub

`docker push sillydong/xgo-centos-{VERSION}`

run build latest

`docker build -t sillydong/latest`

push to docker hub

`docker push sillydong/xgo-centos-latest`

done
