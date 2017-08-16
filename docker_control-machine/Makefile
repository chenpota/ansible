IMAGE_NAME=docker_control-machine:ubuntu16.amd64

.PHONY: all
all: build

.PHONY: build
build:
	docker build \
		-t ${IMAGE_NAME} \
		--no-cache \
		--pull \
		.

.PHONY: clean
clean:
	docker rmi ${IMAGE_NAME} || true
