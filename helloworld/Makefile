.PHONY: all
all: .helloworld

REV:=$(shell git rev-parse --short HEAD)

.helloworld: helloworld-linux-amd64 Dockerfile
	docker build --build-arg "VCS_REF=${REV}" -t quay.io/weaveworks/helloworld:master-${REV} .
	touch $@

helloworld-linux-amd64: helloworld.go
	env GOOS=linux GOARCH=amd64 go build -tags netgo -ldflags="-X main.rev=${REV}" -o $@ $*

.PHONY: clean
clean:
	rm -f .helloworld helloworld-linux-amd64

